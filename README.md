def calculator():
    print("Simple Calculator")
    print("Enter 'exit' to quit")

    while True:
        expr = input("Enter operation (e.g. 3 + 4): ").strip()
        if expr.lower() == 'exit':
            print("Goodbye!")
            break

        try:
            # Safe evaluation of simple arithmetic expressions
            # Only allow digits, operators, spaces
            if not all(c in "0123456789+-*/. ()" for c in expr):
                raise ValueError("Invalid characters detected.")
            
            result = eval(expr)
            print(f"Result: {result}")
        except Exception as e:
            print(f"Error: {e}")

if __name__ == "__main__":
    calculator()
