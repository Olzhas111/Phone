# Phone
public class Phone {

    private int number;
    private String model;
    private int weight;

    Phone(  int number, String model, int weight){
        this.number = number;
        this.model = model;
        this.weight = weight;
    }

    Phone(int number, String model){
        this.number = number;
        this.model = model;
    }

    Phone(){

    }

    public int getNumber(){
        return number;
    }
    public String getModel(){
        return model;
    }
    public int getWeight(){
        return weight;
    }
    //г) Добавить в класс Phone методы: receiveCall, имеет один параметр – имя звонящего. Выводит на консоль
    // сообщение “Звонит {name}”. getNumber – возвращает номер телефона. Вызвать эти методы для каждого из объектов.

   public int receiveCall(String callerName){
       System.out.println(callerName + " is calling");
       return getNumber();
   }

    // Добавьте перегруженный метод receiveCall, который принимает два параметра - имя звонящего и номер телефона
    // звонящего. Вызвать этот метод.
    public int receiveCall(String callerName, int number){
        System.out.println(callerName + " is calling");
        number = getNumber();
        return number;
    }
    //к) Создать метод sendMessage c аргументами переменной длины. Данный метод принимает на вход номера телефонов,
    // которым будет отправлено сообщение. Метод выводит на консоль номера этих телефонов.


}
import java.util.Random;

public class WorkPhone {

    public static void main(String[] args) {
//б) Создайте три экземпляра этого класса.
        Phone phone1 = new Phone(59595, "Nokia", 100);
        Phone phone2 = new Phone(595344, "Apple", 50);
        Phone phone3 = new Phone(595455, "Samsung", 40);
        Phone phoneArray[] = {phone1,phone2,phone3};

        Phone phoneEmpty = new Phone(12456,"Xiaomi", 0);


        //в) Выведите на консоль значения их переменных.
        for (int i = 0; i < phoneArray.length; i++) {
            System.out.println(phoneArray[i].getModel()+" has weight of "+ phoneArray[i].getWeight()+
                    " gramms, and snumber is : " + phoneArray[i].getNumber());
        }
        System.out.println("------------------------------------------------------------");
        //г) Добавить в класс Phone методы: receiveCall, имеет один параметр – имя звонящего. Выводит на консоль
        // сообщение “Звонит {name}”. getNumber – возвращает номер телефона. Вызвать эти методы для каждого из объектов.
        for (int j = 0; j < phoneArray.length ; j++) {
            System.out.println(phoneArray[j].receiveCall("Ameer"));
            System.out.println("------------------------------------------------------------");
            System.out.println(phone1.receiveCall("Ameer", phone1.getNumber()));
        }
    }
