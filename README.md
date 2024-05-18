# trabalho_heran-a

Crie um programa para calcular o salário dos funcionários de uma empresa. O salário é baseado no valor hora e quantidade de horas trabalhadas no mês. Porém, para algumas funçõeses existe uma bonificaçãoo. Para os líderes, o salário é incrementado em 2% e para os gerentes em 5%. Desenvolva o diagrama de classe da UML.
// Classe Employee
class Employee {
    private String name;
    private double hourlyRate;
    private int hoursWorked;
   
    public Employee(String name, double hourlyRate, int hoursWorked) {
        this.name = name;
        this.hourlyRate = hourlyRate;
        this.hoursWorked = hoursWorked;
    }
   
    public double calculateSalary() {
        return hourlyRate * hoursWorked;
    }
}

// Subclasse Leader
class Leader extends Employee {
    public Leader(String name, double hourlyRate, int hoursWorked) {
        super(name, hourlyRate, hoursWorked);
    }
   
    @Override
    public double calculateSalary() {
        // Incrementa 2% ao salário base
        return super.calculateSalary() * 1.02;
    }
}

// Subclasse Manager
class Manager extends Employee {
    public Manager(String name, double hourlyRate, int hoursWorked) {
        super(name, hourlyRate, hoursWorked);
    }
   
    @Override
    public double calculateSalary() {
        // Incrementa 5% ao salário base
        return super.calculateSalary() * 1.05;
    }
}

// Classe Main
public class Main {
    public static void main(String[] args) {
        // Exemplo de uso
        Employee employee1 = new Employee("João", 20.0, 160);
        Leader leader1 = new Leader("Maria", 25.0, 160);
        Manager manager1 = new Manager("Carlos", 30.0, 160);
       
        System.out.println("Salário do funcionário João: R$" + employee1.calculateSalary());
        System.out.println("Salário da líder Maria: R$" + leader1.calculateSalary());
        System.out.println("Salário do gerente Carlos: R$" + manager1.calculateSalary());
    }
}
