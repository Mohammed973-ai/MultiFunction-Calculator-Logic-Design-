# Multifunction Calculator: 4-Bit Integrated Circuit Design

This project is a hardware-level simulation of a **4-bit Multifunction Calculator**.


## 📖 Project Overview
The calculator is a basic system that can add, subtract, multiply, divide, and store numbers using logic gates and integrated circuits.

## **Core Features**
* **Arithmetic Operations**: Performs addition, subtraction, multiplication, and division.
* **Memory Management**: Includes a dedicated unit to store, recall, and clear numerical data.
* **Visual Output**: Converts binary operational results into a human-readable format via 7-segment displays.

## **Technical Limitations**
* **Input Size**: Supports 4-bit binary inputs only.
* **Data Constraints**: Does not handle negative numbers or fractions.


## 🛠️ Circuit Architecture

## **1. Input Unit**
* **Function**: Takes two 4-bit numbers from the user via switches.
* **Logic**: Switches are configured to send a `0` (Ground) when pressed and `VCC` when released.
* **Signal Activation**: Pressing a specific button activates the corresponding operation signal (e.g., ADD), routing the data to the correct processing unit.

<img width="680" height="738" alt="image" src="https://github.com/user-attachments/assets/f2362621-5adb-4b3a-8fb0-5378a6344361" />


---

## **2. Add Unit**
* Uses a **74283 4-bit adder** to sum the two inputs when the add signal is triggered.

<img width="1359" height="531" alt="image" src="https://github.com/user-attachments/assets/510cd9a3-bf4b-471e-83d2-9343466d97e8" />

---

## **3. Sub Unit**
* Employs the 4-bit adder with XOR gates to implement **2's Complement** logic.
* A correction circuit (XOR and NOT gates) ensures the result is always the subtraction of the smaller number from the larger one.

<img width="933" height="460" alt="image" src="https://github.com/user-attachments/assets/c0cc4fe8-8dbb-4c1a-9854-ff21631b716d" />

---

## **4. Multiply Unit**:
* Implements a **"Paper and Pencil" algorithm** using AND gates for partial products and 4-bit adders for summation.

<img width="974" height="473" alt="image" src="https://github.com/user-attachments/assets/72bad404-bfc5-48c3-bd75-d112fabb373c" />

---

## **5. Division Unit**: 
* Utilizes a **Non-Restoring Algorithm**; it compares the dividend and divisor to determine quotient bits, placing a `1` if the dividend is larger and subtracting the divisor.

<img width="943" height="839" alt="image" src="https://github.com/user-attachments/assets/179019b5-344d-4a5f-b672-d067339aff59" />

---

## **6. Memory Unit**
This unit manages numerical persistence through four signals:
* **M+ (Memory Add)**: Adds the current input to the existing value in memory.
* **M- (Memory Subtract)**: Subtracts the input from the stored value using a 4-bit carry ripple adder.
* **MR (Memory Recall)**: Outputs the stored value to a **tri-state buffer** when activated.
* **MC (Memory Clear)**: Resets memory to zero by adding $0 + 0$ and storing the result.
* **Clock Logic**: Registers are **active-low**; since buttons send a `0` when pressed, an AND gate is used to trigger storage whenever any operation button is activated.

<img width="988" height="411" alt="image" src="https://github.com/user-attachments/assets/68054610-a5d1-4762-b8ae-1730293e5bf1" />

---

## **7. Output Unit**
* **Conversion**: Operational results are converted to Binary Coded Decimal (BCD) using the **Double Dabble Algorithm**.
* **Display**: A **BCD-to-7-segment decoder** drives the final output for visual representation.

<img width="543" height="464" alt="image" src="https://github.com/user-attachments/assets/b1a31462-283f-4956-a0f5-4b3d16248384" />



## 🎓 Academic Context
* **Institution**: Zagazig University, Faculty of Engineering.
* **Department**: Computer and Systems Engineering (Third Year).
* **Developer**: Mohamed Waseem Mohamed.
* **Academic Year**: 2023/2024.
