package assignment1;

class complex {
    double real;
    double imaginary;
    //Default Constructor
    public complex(){
        this.real=0;
        this.imaginary=0;
    }
    //Parameterized Constructor
    public complex(double real, double imaginary){
        this.real=real;
        this.imaginary=imaginary;
    }
    //Method to add
    public complex add(complex other){
        return new complex(this.real+other.real, this.imaginary+other.imaginary);
    }
    //Method to subtract 
    public complex subtract(complex other){
        return new complex(this.real-other.real, this.imaginary-other.imaginary);
    }
    //Method to multiply
    public complex multiply(complex other){
        return new complex(this.real*other.real-this.imaginary*other.imaginary, this.real*other.imaginary+this.imaginary*other.real);
    }
    //Method to divide
    public complex divide(complex other){
        double denom= other.real*other.real + other.imaginary*other.imaginary;
        return new complex((this.real*other.real+this.imaginary*other.imaginary)/denom, (this.imaginary*other.real-this.real*other.imaginary)/denom);
    }
    public void display(){
        System.out.println(real+"i"+imaginary);
    }
}
    public class practice2{
        public static void main(String[]args){
            //creating complex numbers
            complex num1=new complex(4,5);
            complex num2=new complex(6,7);
            
            //for addition
            complex sum=num1.add(num2);
            System.out.println("Addition: ");
            sum.display();
            
            //for subtraction
            complex difference=num1.subtract(num2);
            System.out.println("Subtraction: ");
            difference.display();
            
            //for multiplication
            complex multiple=num1.multiply(num2);
            System.out.println("Multiplication: ");
            multiple.display();
            
            //for division
            complex div=num1.divide(num2);
            System.out.println("Division: ");
            div.display();
            
        }
    }