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
