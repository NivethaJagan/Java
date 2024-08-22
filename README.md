package com.customer.demo;


	import java.time.LocalDate;

	public class Customer {
	    private int custId;
	    private String custName;
	    private String city;
	    private double premium;
	    private LocalDate dateOfBirth;

	    public Customer(int custId, String custName, String city, double premium, LocalDate dateOfBirth) {
	        this.custId = custId;
	        this.custName = custName;
	        this.city = city;
	        this.premium = premium;
	        this.dateOfBirth = dateOfBirth;
	    }

	    public int getCustId() {
	        return custId;
	    }

	    public String getCustName() {
	        return custName;
	    }

	    public String getCity() {
	        return city;
	    }

	    public double getPremium() {
	        return premium;
	    }

	    public LocalDate getDateOfBirth() {
	        return dateOfBirth;
	    }

	    @Override
	    public String toString() {
	        return "Customer{" +
	                "custId=" + custId +
	                ", custName='" + custName + '\'' +
	                ", city='" + city + '\'' +
	                ", premium=" + premium +
	                ", dateOfBirth=" + dateOfBirth +
	                '}';
	    }
	}

package com.customer.demo;
import java.time.LocalDate;
import java.util.ArrayList;
import java.util.List;

public class CustomerDemo {

    public static void main(String[] args) {
        
        List<Customer> customers = new ArrayList<>();

        
        customers.add(new Customer(1, "Nivetha", "Delhi", 85000, LocalDate.of(1990, 6, 15)));
        customers.add(new Customer(2, "Santhiya", "Delhi", 95000, LocalDate.of(1985, 9, 22)));
        customers.add(new Customer(3, "Deepika", "Mumbai", 70000, LocalDate.of(1988, 4, 11)));
        customers.add(new Customer(4, "Nirupama", "Delhi", 50000, LocalDate.of(1992, 12, 5)));
        customers.add(new Customer(5, "Harivardhani", "Delhi", 90000, LocalDate.of(1987, 7, 30)));
        customers.add(new Customer(6, "Nithisharika", "Bangalore", 100000, LocalDate.of(1989, 1, 10)));
        customers.add(new Customer(7, "Sangeetha", "Delhi", 82000, LocalDate.of(1991, 5, 25)));
        customers.add(new Customer(8, "Anu", "Delhi", 75000, LocalDate.of(1984, 8, 19)));
        customers.add(new Customer(9, "Ashika", "Mumbai", 65000, LocalDate.of(1986, 10, 2)));
        customers.add(new Customer(10, "Mritulla", "Delhi", 110000, LocalDate.of(1993, 1, 1)));

        
        System.out.println("All Customers:");
        customers.forEach(System.out::println);

        System.out.println("\nCustomers with premium > 80000:");
        customers.stream()
                .filter(c -> c.getPremium() > 80000)
                .forEach(System.out::println);

        System.out.println("\nCustomers from Delhi:");
        customers.stream()
                .filter(c -> "Delhi".equals(c.getCity()))
                .forEach(System.out::println);

        System.out.println("\nCustomers sorted by date of birth:");
        customers.stream()
                .sorted((c1, c2) -> c1.getDateOfBirth().compareTo(c2.getDateOfBirth()))
                .forEach(System.out::println);

        System.out.println("\nCustomers sorted by name:");
        customers.stream()
                .sorted((c1, c2) -> c1.getCustName().compareTo(c2.getCustName()))
                .forEach(System.out::println);
    }
}
