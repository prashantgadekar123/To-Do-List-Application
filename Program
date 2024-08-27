using System;

namespace ToDoListApp
{
    class Program
    {
        static void Main(string[] args)
        {
            TaskManager taskManager = new TaskManager();
            bool running = true;

            while (running)
            {
                Console.WriteLine("To-Do List Application");
                Console.WriteLine("1. View All Tasks");
                Console.WriteLine("2. Add New Task");
                Console.WriteLine("3. Edit Task");
                Console.WriteLine("4. Complete Task");
                Console.WriteLine("5. Delete Task");
                Console.WriteLine("6. Exit");
                Console.Write("Select an option: ");

                string choice = Console.ReadLine();

                switch (choice)
                {
                    case "1":
                        taskManager.ListTasks();
                        break;
                    case "2":
                        Console.Write("Enter task description: ");
                        string description = Console.ReadLine();
                        taskManager.AddTask(description);
                        Console.WriteLine("Task added successfully.");
                        break;
                    case "3":
                        Console.Write("Enter task ID to edit: ");
                        int editId = int.Parse(Console.ReadLine());
                        Console.Write("Enter new description: ");
                        string newDescription = Console.ReadLine();
                        taskManager.EditTask(editId, newDescription);
                        Console.WriteLine("Task updated successfully.");
                        break;
                    case "4":
                        Console.Write("Enter task ID to complete: ");
                        int completeId = int.Parse(Console.ReadLine());
                        taskManager.CompleteTask(completeId);
                        Console.WriteLine("Task marked as completed.");
                        break;
                    case "5":
                        Console.Write("Enter task ID to delete: ");
                        int deleteId = int.Parse(Console.ReadLine());
                        taskManager.DeleteTask(deleteId);
                        Console.WriteLine("Task deleted successfully.");
                        break;
                    case "6":
                        running = false;
                        break;
                    default:
                        Console.WriteLine("Invalid option, try again.");
                        break;
                }
                Console.WriteLine();
            }
        }
    }
}
