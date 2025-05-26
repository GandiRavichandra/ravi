# todo_list.py

tasks = []

def show_menu():
    print("\n==== TO-DO LIST MENU ====")
    print("1. View Tasks")
    print("2. Add Task")
    print("3. Mark Task as Completed")
    print("4. Delete Task")
    print("5. Exit")

def view_tasks():
    if not tasks:
        print("No tasks in your to-do list.")
    else:
        print("\nYour Tasks:")
        for i, task in enumerate(tasks, start=1):
            status = "✅" if task["completed"] else "❌"
            print(f"{i}. {task['title']} [{status}]")

def add_task():
    title = input("Enter task title: ")
    tasks.append({"title": title, "completed": False})
    print("Task added.")

def mark_completed():
    view_tasks()
    try:
        task_no = int(input("Enter task number to mark as completed: "))
        if 1 <= task_no <= len(tasks):
            tasks[task_no - 1]["completed"] = True
            print("Task marked as completed.")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

def delete_task():
    view_tasks()
    try:
        task_no = int(input("Enter task number to delete: "))
        if 1 <= task_no <= len(tasks):
            removed = tasks.pop(task_no - 1)
            print(f"Deleted task: {removed['title']}")
        else:
            print("Invalid task number.")
    except ValueError:
        print("Please enter a valid number.")

# Main loop
while True:
    show_menu()
    choice = input("Enter your choice (1-5): ")

    if choice == '1':
        view_tasks()
    elif choice == '2':
        add_task()
    elif choice == '3':
        mark_completed()
    elif choice == '4':
        delete_task()
    elif choice == '5':
        print("Exiting... Have a productive day!")
        break
    else:
        print("Invalid choice. Please enter a number between 1 and 5.")
