# MetodosOrdenamiento


## Bubble sort

el bubble sort es un algoritmo simple de ordenamiento que recorre una lista y va intercambiando los elementos adyacentes si están en el orden incorrecto. Esto se repite hasta que la lista esté ordenada. Es llamado "bubble" (burbuja) porque los elementos más grandes van "burbujeando" hacia arriba en la lista durante cada iteración. Aunque fácil de entender, no es muy eficiente para grandes cantidades de datos debido a su alto número de comparaciones e intercambios.

### Implementación en código:

```java
public class BubbleSort {
    public static void main(String[] args) {
        int[] arr = {64, 34, 25, 12, 22, 11, 90};
        bubbleSort(arr);
        System.out.println("Array ordenado con Bubble Sort:");
        printArray(arr);
    }

    static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++)
            for (int j = 0; j < n - i - 1; j++)
                if (arr[j] > arr[j + 1]) {
                    // swap temp and arr[i]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
    }

    static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
}
```

### Insertion sort

El insertion sort es un algoritmo de ordenamiento simple y eficiente. Avanza a través de la lista, insertando cada elemento en su posición correcta entre los elementos ya ordenados. Es eficaz para listas pequeñas o casi ordenadas, pero puede ser menos eficiente para listas grandes debido a su complejidad cuadrática.

## Implementación en código.

```java
public class InsertionSort {
    public static void main(String[] args) {
        int[] arr = {12, 11, 13, 5, 6};
        insertionSort(arr);
        System.out.println("Array ordenado con Insertion Sort:");
        printArray(arr);
    }

    static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; ++i) {
            int key = arr[i];
            int j = i - 1;

            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }

    static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
}
```

### Selection sort

el Selection Sort es otro algoritmo de ordenamiento simple. Funciona así:

-Encuentra el elemento más pequeño en la lista y lo intercambia con el primer elemento.
-Luego, encuentra el segundo elemento más pequeño y lo intercambia con el segundo elemento.
-Continúa este proceso hasta que toda la lista esté ordenada.

A diferencia del Bubble Sort, que compara elementos adyacentes, el Selection Sort busca el elemento más pequeño y lo coloca en su posición correcta en cada iteración. Aunque también simple, puede ser ineficiente para grandes conjuntos de datos debido a su naturaleza cuadrática.

## Implementación en código:
```java
public class SelectionSort {
    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        selectionSort(arr);
        System.out.println("Array ordenado con Selection Sort:");
        printArray(arr);
    }

    static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++)
                if (arr[j] < arr[minIndex])
                    minIndex = j;
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }

    static void printArray(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
}
```
