# COP2664-1-Lesson-7-Programming-Exercise-7.1-Task-Manager-System
This is a GitHub repository link for the first Programming Exercise of Module 7.

// This program is used to create a task application that manages tasks with different states of progress.

enum TaskState {
  case pending, inProgress, completed
}
// This enum represents the different states of a task.

struct TaskDetails {
  var priority: String
  var dueDate: String
}
// Declaring the TaskDetails struct to store the priority and due date of the task.

class Task {
  var title: String
  var state: TaskState
  var description: String
  var details: TaskDetails
    // Declaring the properties of the Task class.

  init(title: String, state: TaskState, description: String, details: TaskDetails) {
      self.title = title
      self.state = state
      self.description = description
      self.details = details
  }
    // Initializing the Task class with the given parameters.

  func markInProgress() {
      if state == .pending {
          state = .inProgress
      }
  }
    // Method to mark the task as in progress.

  func markCompleted() {
      if state == .inProgress {
          state = .completed
      }
  }
    // Method to mark the task as completed.

  func displayTaskDetails() {
      print("Task: \(title)")
      print("State: \(state)")
      print("Description: \(description)")
      print("Priority: \(details.priority)")
      print("Due Date: \(details.dueDate)\n")
  }
}
// Declaring the Task class to represent a task with different states of progress.

let task1 = Task(title: "Dog Walking", state: .pending, description: "Walk the dog around the block for one hour.", details: TaskDetails(priority: "Low", dueDate: "2025-3-26"))
let task2 = Task(title: "Housechores", state: .completed, description: "Vacuum the house and do the dishes.", details: TaskDetails(priority: "Medium", dueDate: "2025-3-28"))
let task3 = Task(title: "Homework", state: .inProgress, description: "Complete the algebra homework.", details: TaskDetails(priority: "High" , dueDate: "2025-3-30"))
// Creating three tasks with different states of progress.

task1.markCompleted()
task1.displayTaskDetails()
task2.markCompleted()
task2.displayTaskDetails()
task3.markInProgress()
task3.displayTaskDetails()
// Marking the tasks as completed and displaying their details.
