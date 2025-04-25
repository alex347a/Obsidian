![[07 Debugging, data collection and visualization Slide.pdf]]

| Slide: | Concept:                                                          |
| ------ | ----------------------------------------------------------------- |
| 1-46   | Debugging and troubleshooting                                     |
| 5-13   | Common errors                                                     |
| 14-46  | Debugging techniques                                              |
| 20-24  | LED and GPIO                                                      |
| 25-40  | Logging                                                           |
| 41-46  | Monitoring Memory Usage                                           |
| 41-72  | Data collection                                                   |
| 41-58  | Kvalitativ vs. kvalitativ, og hvorfor data collection er vigtigt? |
| 59-72  | End-to-end Data collection                                        |
| 73-91  | Data visualization                                                |

Precision versus Accuracy (Precision vs accuracy)
![[Precision versus accuracy.png]]
**Debugging and Troubleshooting**

- The process of identifying, isolating, and resolving issues or bugs in a program or hardware setup.

**Common Errors**

- Frequent mistakes in programming or circuits, such as syntax errors, runtime errors, and logical errors that need correction.
- **Syntax Errors**
    - These occur when code does not follow the language’s syntax rules, such as missing punctuation, incorrect keywords, or mismatched brackets. Syntax errors prevent the code from compiling or running.
    
- **Runtime Errors**
    - Errors that happen while the program is running. These include issues like division by zero, file not found, or accessing out-of-bounds elements in an array. Runtime errors can cause programs to crash unexpectedly.
    
- **Logical Errors**
    - These errors occur when code runs without crashing but produces incorrect results due to flaws in the program's logic. For example, using the wrong formula or incorrect conditions in loops.
    
- **Type Errors**
    - Occurs when operations are applied to incompatible data types, such as adding a string to an integer. These errors can be caught in languages with strict type checking, while dynamic languages might fail only during execution.
    
- **Off-by-One Errors**
    - A common error in loops where the loop iterates one time too many or one time too few, often due to incorrect start or end conditions.
    
- **Null or Undefined References**
    - These errors happen when a program tries to use a variable that has no value assigned, which can lead to crashes or unexpected behavior, especially in languages with pointers or references.
    
- **Infinite Loops**
    - Occurs when loop conditions are never met, causing the program to loop indefinitely. These errors can freeze the program and make it unresponsive.
    
- **Overflows and Underflows**
    - Occurs when a calculation exceeds the maximum or minimum limit a data type can hold, which can lead to incorrect calculations or unexpected behaviour, especially in numerical computations.
    
- **Resource Leaks**
    - Happens when resources like memory or file handles are not released after use, causing the system to run out of resources over time (e.g., memory leaks in languages without automatic garbage collection).
    
- **Hardware Connection Errors**
    - In hardware setups, wiring mistakes or loose connections in circuits can prevent components like sensors or LEDs from functioning correctly, often causing unpredictable results.
    
- **Misconfigured Settings**
    - Configuration errors can occur if settings (e.g., network parameters, file paths, or API keys) are incorrect, leading to issues with connectivity, data access, or permissions.

**Debugging Techniques**

- Methods for systematically finding and fixing bugs, including breakpoints, step-by-step execution, and print statements.

**LED and GPIO**

- LEDs (Light Emitting Diodes) can be controlled by GPIO (General-Purpose Input/Output) pins, commonly used for visual debugging or signalling in circuits.

**Logging**

- Recording information about a program’s operation (e.g., error messages, function execution) to help diagnose issues and track performance.

**Monitoring Memory Usage**

- Tracking memory allocation in a program to prevent leaks or overuse, which could slow down or crash a system.

**Data Collection**

- The process of gathering relevant information for analysis, often used to make informed decisions and improve system performance.

**Qualitative vs. Quantitative Data, and Why Data Collection is Important**

- Qualitative data captures non-numeric insights (like opinions), while quantitative data provides measurable, numeric information. Data collection is essential for creating accurate models and making data-driven decisions.

**End-to-End Data Collection**

- Gathering data from the beginning to the end of a process, ensuring comprehensive insights and enabling full system analysis.
- The purpose is to identify patterns, bottlenecks, or areas for improvement by having data from every stage, enabling better analysis and decision-making.

**Data Visualization**

- The graphical representation of data (e.g., charts, graphs) to help interpret patterns, trends, and insights more effectively.
- Common visualization types include bar charts, line graphs, scatter plots, and heat maps. Each type helps highlight different insights, such as trends, comparisons, or distributions.
- Effective visualization enables stakeholders to interpret large amounts of data quickly, recognize patterns, and communicate insights to non-technical audiences, supporting informed decision-making.