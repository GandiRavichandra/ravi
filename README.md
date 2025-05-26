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
