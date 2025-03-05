Single Responsibility Principle (SRP) - Principio de Responsabilidad Única
// Incorrecto: La clase tiene más de una responsabilidad (gestionar empleados y generar reportes).
public class Employee
{
    public string Name { get; set; }
    public void SaveToDatabase() 
    {
        Console.WriteLine("Empleado guardado en la base de datos.");
    }
    public void GenerateReport() 
    {
        Console.WriteLine("Reporte generado.");
    }
}

// Correcto: Separar responsabilidades en diferentes clases.
public class Employee
{
    public string Name { get; set; }
}

public class EmployeeRepository
{
    public void SaveToDatabase(Employee employee) 
    {
        Console.WriteLine("Empleado guardado en la base de datos.");
    }
}

public class ReportGenerator
{
    public void GenerateReport(Employee employee) 
    {
        Console.WriteLine("Reporte generado.");
    }
}
