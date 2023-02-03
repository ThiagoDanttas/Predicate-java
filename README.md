# Predicate - java

---

[Documentação Predicate\<T>](https://docs.oracle.com/javase/10/docs/api/java/util/function/Predicate.html)


~~~~java
public interface Predicate<T> {
    boolean test (T t);
}
~~~~

### Versões de implementação Predicate:

• Implementação da interface <br>
~~~~java
public class ProductPredicate implements Predicate<Product> {
    
    @Override
    public boolean test(Product p) {
        return p.getPrice() >= 100.0;
    }
}
~~~~
• Reference method com método estático<br>
• Reference method com método não estático<br>
~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));

		double min = 100.0;

		list.removeIf(Product::staticProductPredicate); // <-- Observação

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~
• Expressão lambda declarada<br>

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));

                double min = 100.0; // Permite a utilização de variáveis
        
		Prdicate<Product> pred = p -> p.getPrice() >= min;

		list.removeIf(pred); // <-- Observação

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~

• Expressão lambda inline

~~~~java

public class Program {

	public static void main(String[] args) {

		List<Product> list = new ArrayList<>();

		list.add(new Product("Tv", 900.00));
		list.add(new Product("Mouse", 50.00));
		list.add(new Product("Tablet", 350.50));
		list.add(new Product("HD Case", 80.90));
        
		list.removeIf(p -> p.getPrice() >= 100.0); // <-- Observação

		for (Product p : list) {
			System.out.println(p);
		}
	}
}
~~~~