# Ensure the lists are properly initialized (if not already from previous cells)
daily_tasks = ['Finish project report', 'Attend team meeting', 'Review code changes', 'Prepare presentation slides','complete assesment','run scan'] # Example
completed_tasks = []
incomplete_tasks = []

print("\n--- Review Your Daily Tasks ---")
# Create a copy to iterate, as we'll modify the original daily_tasks list
tasks_to_review = list(daily_tasks)

for task in tasks_to_review:
    while True:
        user_input = input(f"Did you complete '{task}'? (y/n): ").strip().lower()
        if user_input == 'y':
            completed_tasks.append(task)
            daily_tasks.remove(task) # Remove from daily tasks once reviewed
            print(f"'{task}' moved to Completed Tasks.")
            break
        elif user_input == 'n':
            incomplete_tasks.append(task)
            daily_tasks.remove(task) # Remove from daily tasks once reviewed
            print(f"'{task}' moved to Incomplete Tasks.")
            break
        else:
            print("Invalid input. Please enter 'y' for yes or 'n' for no.")

print("\n--- Daily Task Review Complete ---")

# Display the final status of all tasks
print("\n--- CURRENT STATUS ---")
print("Daily Tasks (Remaining/Uncategorized):", daily_tasks)
print("Completed Tasks:", completed_tasks)
print("Incomplete Tasks:", incomplete_tasks)
