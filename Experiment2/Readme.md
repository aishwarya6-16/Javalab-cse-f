#experiment2
## TITLE: 2a.) Implement class mechanism in java 
```
class myclass {
    void displaymessage() {
        System.out.println("welcome to java");
    }
    int add (int a, int b) {
        return a+b;
    }
    public static void main(String[] args) {
        myclass obj = new myclass();
        obj.displaymessage();
        int result = obj.add(10, 20);
        System.out.println("sum: " + result);
    }
}
```
# OUTPUT
![EXPERIMENT 2 OUTPUT](exp2a.png)
## TITLE: 2b.) java program implement method overloading
```
class OverloadExample {
    int add(int a, int b) {
        return (a + b);
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    public static void main(String[] args) {
        OverloadExample obj = new OverloadExample();
        int sum1 = obj.add(10, 20);
        double sum2 = obj.add(5.5, 6.5);
        int sum3 = obj.add(10, 20, 30);
        System.out.println("Result of adding two integers: " + sum1);
        System.out.println("Result of adding two double values: " + sum2);
        System.out.println("Result of adding three integers: " + sum3);
    }
}
```
# OUTPUT
![EXPERIMENT 2 OUTPUT](exp2b.png)
