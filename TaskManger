using System;
using System.Collections.Generic;
using System.IO;
using Newtonsoft.Json;

namespace ToDoListApp
{
    public class TaskManager
    {
        private readonly string _filePath = "tasks.json";
        private List<Task> _tasks;

        public TaskManager()
        {
            LoadTasks();
        }

        private void LoadTasks()
        {
            if (File.Exists(_filePath))
            {
                var json = File.ReadAllText(_filePath);
                _tasks = JsonConvert.DeserializeObject<List<Task>>(json) ?? new List<Task>();
            }
            else
            {
                _tasks = new List<Task>();
            }
        }

        private void SaveTasks()
        {
            var json = JsonConvert.SerializeObject(_tasks, Formatting.Indented);
            File.WriteAllText(_filePath, json);
        }

        public void AddTask(string description)
        {
            int nextId = _tasks.Count > 0 ? _tasks[^1].Id + 1 : 1;
            _tasks.Add(new Task { Id = nextId, Description = description, IsCompleted = false });
            SaveTasks();
        }

        public void EditTask(int id, string newDescription)
        {
            var task = _tasks.Find(t => t.Id == id);
            if (task != null)
            {
                task.Description = newDescription;
                SaveTasks();
            }
        }

        public void CompleteTask(int id)
        {
            var task = _tasks.Find(t => t.Id == id);
            if (task != null)
            {
                task.IsCompleted = true;
                SaveTasks();
            }
        }

        public void DeleteTask(int id)
        {
            _tasks.RemoveAll(t => t.Id == id);
            SaveTasks();
        }

        public void ListTasks()
        {
            if (_tasks.Count == 0)
            {
                Console.WriteLine("No tasks available.");
                return;
            }

            foreach (var task in _tasks)
            {
                Console.WriteLine($"{task.Id}. {task}");
            }
        }
    }
}
