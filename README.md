# codesoft_taskno1
#PYTHON PROGRAMMING FOR TO DO LIST FOR CODESOFT INTERNSHIP TASK
# to_do_list.py
todo_list = []

def show_menu():
    print("\n==== TO-DO LIST MENU ====")
    print("1. Add Task")
    print("2. View Tasks")
    print("3. Mark Task as Done")
    print("4. Remove Task")
    print("5. Exit")

def add_task():
    task = input("Enter the task: ")
    todo_list.append({"task": task, "done": False})
    print("Task added.")

def view_tasks():
    if not todo_list:
        print("No tasks in the list.")
    else:
        for idx, item in enumerate(todo_list, 1):
            status = "✓" if item["done"] else "✗"
            print(f"{idx}. [{status}] {item['task']}")

def mark_done():
    view_tasks()
    index = int(input("Enter task number to mark as done: ")) - 1
    if 0 <= index < len(todo_list):
        todo_list[index]["done"] = True
        print("Task marked as done.")
    else:
        print("Invalid task number.")

def remove_task():
    view_tasks()
    index = int(input("Enter task number to remove: ")) - 1
    if 0 <= index < len(todo_list):
        removed = todo_list.pop(index)
        print(f"Removed task: {removed['task']}")
    else:
        print("Invalid task number.")

while True:
    show_menu()
    choice = input("Choose an option: ")
    if choice == "1":
        add_task()
    elif choice == "2":
        view_tasks()
    elif choice == "3":
        mark_done()
    elif choice == "4":
        remove_task()
    elif choice == "5":
        print("Goodbye!")
        break
    else:
        print("Invalid choice. Try again.")
