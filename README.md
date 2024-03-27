# CoRTOS (Cooperative Real-Time Operating System)

CoRTOS is a lightweight, cooperative real-time operating system (RTOS) designed for use in microcontrollers and small embedded systems. It provides a simple framework for managing multiple tasks in a time-critical environment, where simplicity and efficiency are key. With CoRTOS, developers can easily schedule tasks, manage their execution, and handle inter-task communication in a resource-constrained environment.

## Features

- **Task Management:** Efficient creation, scheduling, and management of tasks with support for priorities and flags.
- **Memory Efficiency:** Designed to be minimalistic, making it suitable for devices with limited memory resources.
- **Debugging Support:** Optional debugging features to aid development and troubleshooting, including task naming and CPU usage analytics.
- **Flexible Task Scheduling:** Supports periodic, one-shot, and delayed tasks with easy configuration of task behavior.
- **Task Control:** Provides functions for sleeping tasks, setting their priorities, and managing task flags for fine-grained control over task execution.
- **Cooperative Multitasking:** Tasks cooperatively yield control, allowing for simple and predictable task switching mechanisms.

## Getting Started

### Prerequisites

Ensure you have a C++ compiler and the necessary development tools for your target microcontroller or embedded system.

### Installation

1. Clone the repository to your local machine or download the source code.
2. Include the `CoRTOS.h` header file in your project.
3. Initialize the CoRTOS object and configure it according to your project's needs.

### Example Usage

Below is a simple example demonstrating how to create and register a task with CoRTOS:

```cpp
#include "CoRTOS.h"

// Task function
void blinkLED() {
    // Toggle LED logic here
}

// Setup function
void setup() {
    cortos.init(); // Initialize CoRTOS
    cortos.registerTask(blinkLED, 1, 0); // Register the blinkLED task with priority 1
}

// Main loop
void loop() {
    cortos.scheduler(); // Run the CoRTOS scheduler
}
```