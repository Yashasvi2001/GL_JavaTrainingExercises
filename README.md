# GL_JavaTrainingExercises

//WAP to create anonymous class for mathematical operation such as add, subtract, multiply, divide based on an interface for operation

package pkgDay6;

interface MathOp {
	int operation(int x, int y);
}

public class Day6Ex2Anonymous {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
        //Add
		MathOp add = new MathOp() {
			public int operation(int x, int y) {
				return x + y;
			}
		};
		
		// Substract
		MathOp subtract = new MathOp() {
			public int operation(int x, int y) {
				return x - y;
			}
		};
		
		// Multiply
		MathOp multiply = new MathOp() {
			public int operation(int x, int y) {
				return x * y;
			}
		};
		// divide
		MathOp divide = new MathOp() {
			public int operation(int x, int y) {
				if (y != 0) {
					return x / y;
				} else {
					throw new IllegalArgumentException("Cannot divide by zero.");
				}
			}
		};

		System.out.println("Addition: " + add.operation(11, 8));
		System.out.println("Subtraction: " + subtract.operation(100, 23));
		System.out.println("Multiplication: " + multiply.operation(12, 5));

		try {
			System.out.println("Division: " + divide.operation(10, 2));
		} catch (IllegalArgumentException e) {
			System.out.println("Exception: " + e.getMessage());
		}

		try {
			System.out.println("Division: " + divide.operation(10, 0));
		} catch (IllegalArgumentException e) {
			System.out.println("Exception: " + e.getMessage());
		}
	}
}

Output:
Addition: 19
Subtraction: 77
Multiplication: 60
Division: 5
Exception: Cannot divide by zero.

