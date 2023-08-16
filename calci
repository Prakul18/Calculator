#include<iostream>

using namespace std;

// inp function is used to input the number from user
float inp()
{
    float num;
    cout << "Enter number: ";
    cin >> num;
    return num;
}

// inprad function is used to input radians for sin,cos and tan
float inprad()
{
    float rad;
    cout << "Enter number in radians(taking pi = 3.14) : ";
    cin >> rad;
    return rad;
}

// radcheck func is used to check if number lies between -pi and pi
// if not then it changes the value so it lies between -pi and pi
float radcheck(float numrad)
{
    while (true)
    {
        if (numrad > 3.1415)
        {
            numrad = numrad-6.2832;
        }
        else if (numrad < -3.1415)
        {
            numrad = numrad+6.2832;
        }
        else
        {
            break;
        }
    }
    return numrad;
}

// exp func is used to calculate the exponent n1^n2 by accepting two numbers
float exp(float n1,float n2)
{
    float final = 1;
    for(int i = 0 ; i < n2 ; i++)
            {
                final = final * n1;
            }
    return final;
}

// fact function returns the factorial of a number
int fact(int num)
{
    int factorial = 1;
    for(int j = 1; j <= num ; j++)
    {
        factorial = factorial*j;
    }
    return factorial;
}

// sinfunc uses the taylor series to find the sin of a value
// taylor series sinx = x - x^3/3! + x^5/5! - x^7/7!
float sinfunc(float radnums)
{
    float finalsin = 0 ;
    for(int i=0; i<=4; i++)
    {
        int k = 2*i + 1;
        if(i%2==0)
        {
            finalsin = finalsin + (exp(radnums,k) / fact(k));
        }
        else
        {
            finalsin = finalsin - (exp(radnums,k) / fact(k));
        }
    }
    return finalsin;
}

// cosfunc uses the taylor series to find the cos of a value
// taylor series cosx = 1 - x^2/2! + x^4/4! - x^6/6!
float cosfunc(float radnumc)
{
    float finalcos = 1 ;
    for(int i=1; i<4; i++)
    {
        int k = 2*i;
        if(i%2==0)
        {
            finalcos = finalcos + (exp(radnumc,k) / fact(k));
        }
        else
        {
            finalcos = finalcos - (exp(radnumc,k) / fact(k));
        }
    }
    return finalcos;
}

// main function
int main()
{
    char choice; 
    cout << "WELCOME TO CALCULATOR" << endl;
    cout << "Enter '+' for Addtion" << endl << "Enter '-' for subtraction" << endl;
    cout << "Enter '*' for multiplication" << endl << "Enter '/' for division" << endl;
    cout << "Enter '^' for exponent" << endl << "Enter 's' for sin function" << endl;
    cout << "Enter 'c' for cos function" << endl << "Enter 't' for tan function" << endl;
    cin >> choice; // inputs the choice of mathematical function that the user wants
    float num1, num2, final=1, finrad;
    // switch case is used to determine which mathematical function to be used
    switch (choice)
    {
        case '+' : 
            num1 = inp();
            num2 = inp();
            cout << num1+num2 << " is the addition" << endl;
            break;

        case '-' : 
            num1 = inp();
            num2 = inp();
            cout << num1-num2 << " is the subtraction" << endl;
            break;

        case '*' : 
            num1 = inp();
            num2 = inp();
            cout << num1*num2 << " is the multiplication" << endl;
            break;

        case '/' : 
            num1 = inp();
            num2 = inp();
            if (num2 == 0)
            {
                cout << "THe second number cannot be 0 as answer will be infinite";
                break;
            }
            cout << num1/num2 << " is the division" << endl;
            break;

        case '^' : 
            num1 = inp();
            num2 = inp();
            final = exp(num1,num2);
            cout << final << " is the exponent" << endl;
            break;

        case 's' :
            num1 = inprad();
            finrad = radcheck(num1);
            finrad = sinfunc(finrad);
            cout << finrad << " is the sin of " << num1 << endl;
            break;

        case 'c' :
            num1 = inprad();
            finrad = radcheck(num1);
            finrad = cosfunc(finrad);
            cout << finrad << " is the cos of " << num1 << endl;
            break;

        case 't' :
            num1 = inprad();
            finrad = radcheck(num1);
            finrad = (sinfunc(finrad)/cosfunc(finrad));
            cout << finrad << " is the tan of " << num1 << endl;
            break;

        default : // if given choice does not contain any of the cases
            cout << "Invalid input.";
            break;
    }
    return 0;
}
