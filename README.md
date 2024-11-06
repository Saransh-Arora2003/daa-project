class Queue:
    def _init_(self): 
        self.tasks = []

    def enqueue(self, task):
        self.tasks.append(task)
        print(f"Task added: {task}")     

    def dequeue(self):
        if not self.is_empty():
            return self.tasks.pop(0)
        else:
            return "No tasks to remove."

    def view(self):
        return self.tasks if self.tasks else "No tasks available."

    def is_empty(self):
        return len(self.tasks) == 0

def main():
    queue = Queue()  
    while True:
        print("\nMenu:")
        print("1. Add Task")
        print("2. Remove Task")
        print("3. View Tasks")
        print("4. Exit")
        choice = input("Choose an option: ")

        if choice == '1':
            task = input("Enter task details: ")
            queue.enqueue(task)  
        elif choice == '2':
            removed_task = queue.dequeue()  
            print(removed_task)  
        elif choice == '3':
            tasks = queue.view()  
            print("Current Tasks:", tasks)  
        elif choice == '4':
            print("Exiting...")  
            break
        else:
            print("Invalid choice, please try again.") 

if _name_ == "_main_": 
    main()
