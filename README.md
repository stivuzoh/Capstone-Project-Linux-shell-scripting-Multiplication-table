# Capstone-Project-Linux-shell-scripting-Multiplication-table
Bash script for generating multiplication table
# 🧮 Multiplication Table Script Tutorial

## 📋 Overview
This shell script generates customizable multiplication tables with various options for range and order.

---

## 🖼️ Screenshot 1: The Script Code 

Shows the complete shell script code:

```bash
# Multiplication table script
while true; do
    read -p "Enter a number for the multiplication table: " num
    if ! [[ "$num" =~ ^[0-9]+$ ]]; then
        echo "Invalid input. Please enter a valid number."
        continue
    fi

    read -p "Do you want a full table or a partial table? (f/p): " choice
    if [ "$choice" = "p" ]; then
        read -p "Enter start range (1-10): " start
        read -p "Enter end range (1-10): " end
        if [ "$start" -lt 1 ] || [ "$end" -gt 10 ] || [ "$start" -gt "$end" ]; then
            echo "Invalid range. Showing full table instead."
            start=1
            end=10
        fi
    else
        start=1
        end=10
    fi

    read -p "Do you want the table in ascending or descending order? (a/d): " order
    if [ "$order" = "d" ]; then
        for ((i=end; i>=start; i--)); do
            echo "$num x $i = $((num * i))"
        done
    else
        for ((i=start; i<=end; i++)); do
            echo "$num x $i = $((num * i))"
        done
    fi

    read -p "Do you want to generate another table? (y/n): " again
    if [ "$again" != "y" ]; then
        break
    fi
done
```

**Key Features Visible:**
- 🔄 Main loop structure
- ✅ Input validation with regex
- 🎯 Full/partial table logic
- ⬆️⬇️ Ascending/descending order implementation

---

## 🖼️ Screenshot 2: Partial Table Mode 

![Step2](Step2%20running%20script%20with%20a%20partial%20table%20mode.png)

Demonstrates partial table functionality:

```
Enter a number: 4 → Partial table → Start: 2, End: 9 → Ascending order
Output: 4×2=8 to 4×9=36

Enter a number: 3 → Partial table → Start: 6, End: 8 → Descending order  
Output: 3×8=24, 3×7=21, 3×6=18
```

---

## 🖼️ Screenshot 3: Full Table Mode 

![Step3](Step3%20running%20script%20in%20Full%20table%20mode.png)

Shows full table with both order options:

```
Number: 2 → Full table → Ascending order
2×1=2 to 2×10=20

Number: 5 → Full table → Descending order
5×10=50 to 5×1=5
```

---

## 🖼️ Screenshot 4: Error Handling 

![Step4](Step4%20running%20script%20with%20an%20unknown%20interger.png)

Demonstrates robust input validation:

```
Enter a number: r → ❌ "Invalid input"
Enter a number: f → ❌ "Invalid input" 
Enter a number: g → ❌ "Invalid input"
```

---

## 🎯 Key Learning Points from All Screenshots

### ✅ What Works Well:
- 🛡️ Solid validation against non-numeric input  
- 🔧 Flexible table generation (full/partial, ascending/descending)  
- 🔄 User-friendly flow with clear prompts  
- ♻️ Repeatable execution without restarting  

### 🚀 Real-World Usage Examples:
- Quick full tables for basic multiplication practice  
- Custom ranges for focused learning (like 6–8 times tables)  
- Reverse order for testing recall  
- Continuous practice with multiple numbers in one session  

---

## 🏁 Conclusion

🎉 This script demonstrates excellent shell scripting fundamentals!  
The screenshots prove it's:

✅ Production-ready with proper error handling  
✅ User-tested with real usage examples  
✅ Educationally valuable for learning multiplication  
✅ Technically sound with good code structure  
