public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // В фрейме Stack Memory создается интовая ячейка со значением 1 
        Object o = new Object();        // В куче создается объект Object и ссылка на него в стеке о
        Integer ii = 2;                 // В куче создается интовый объект равный 2 и ссылка на него в стеке ii
        printAll(o, i, ii);             // Создается фрейм в стеке куда передается ссылки o, i, ii
        System.out.println("finished"); // Создается фрейм в стеке куда передается ссылка finished
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // В куче создается интовый объект 700, а ссылка uselessVar передается в стек printAll
        System.out.println(o.toString() + i + ii);  // Создается фрейм в стеке куда передаются ссылки. /b 
        // Сборщик мусора после завершения метода удаляет: фреймы toString переменных, фрейм println, объект, хранящий результат сложения. 
    }
}