/*
 * Calculator.cpp
 *
 *  Date: 7/9/2023
 *  Author: Sandra Nelly Cardenas
 */

#include <iostream>

using namespace std;

// I changed the return type of main from void to int
int main()
{
	// I removed 'statement' as it was declared but never used in the code
	int op1, op2;
	char operation;
	// I fixed the character assignment to 'answer', it should use single quotes ('')
	char answer = 'Y';

	while (answer == 'Y' || answer == 'y') // I modified the condition to accept 'Y' or 'y' as yes
	{
		cout << "Enter expression" << endl;
		// I corrected the order of the cin statement, it should be op1 -> operation -> op2
		cin >> op1 >> operation >> op2;

		// I removed the semicolons at the end of 'if' statements, those were causing errors
		// I used the correct operator '<<' for cout instead of '>>'
		// I also fixed the operator symbols in cout for each operation
		if (operation == '+')
			cout << op1 << " + " << op2 << " = " << op1 + op2 << endl;
		else if (operation == '-')
			cout << op1 << " - " << op2 << " = " << op1 - op2 << endl;
		else if (operation == '*')
			cout << op1 << " * " << op2 << " = " << op1 * op2 << endl;
		else if (operation == '/')
		{
			// I added a check for division by zero, to prevent error
			if (op2 == 0)
			{
				cout << "Error! Division by zero is not allowed." << endl;
			}
			else
			{
				cout << op1 << " / " << op2 << " = " << op1 / op2 << endl;
			}
		}
		else
		{
			cout << "Invalid operation entered." << endl;
		}

		cout << "Do you wish to evaluate another expression? (Y/N)" << endl;
		cin >> answer;
	}
	return 0;
}
