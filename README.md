# Predicate - java

---

[Documenta��o Predicate\<T>](https://docs.oracle.com/javase/10/docs/api/java/util/function/Predicate.html)


~~~~java
public interface Predicate<T> {
    boolean test (T t);
}
~~~~

### Vers�es de implementa��o Predicate:

� Implementa��o da interface <br>
~~~~java
public class ProductPredicate implements Predicate<Product> {
    
    @Override
    public boolean test(Product p) {
        return p.getPrice() >= 100.0;
    }
}
~~~~
� Reference method com m�todo est�tico<br>
� Reference method com m�todo n�o est�tico<br>
~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));

		double min = 100.0;

		list.removeIf(Product::staticProductPredicate); // <-- Observa��o

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~
� Express�o lambda declarada<br>

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));

                double min = 100.0; // Permite a utiliza��o de vari�veis
        
		Prdicate<Product> pred = p -> p.getPrice() >= min;

		list.removeIf(pred); // <-- Observa��o

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~

� Express�o lambda inline

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));
        
		list.removeIf(p -> p.getPrice() >= 100.0); // <-- Observa��o

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~