import java.util.Arrays;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        
        byte[] byteArray = new byte[5];
        Byte[] byteArrayObj = new Byte[5];
        char[] charArray = new char[5];
        Character[] charArrayObj = new Character[5];
        short[] shortArray = new short[5];
        Short[] shortArrayObj = new Short[5];
        int[] intArray;
        intArray = new int[5];
        Integer[] intArrayObj = new Integer[5];
        long[] longArray = new long[5];
        Long[] longArrayObj = new Long[5];
        float[] floatArray = new float[5];
        Float[] floatArrayObj = new Float[5];
        double[] doubleArray = new double[5];
        Double[] doubleArrayObj = new Double[5];
        Object[] objectArray = new Object[5];
        String[] stringArray = new String[5];

       
        for (int i = 0; i < 5; i++) {
            byteArray[i] = (byte) (i + 1);
            byteArrayObj[i] = (byte) (i + 1);
            charArray[i] = (char) (i + 65); // ASCII values
            charArrayObj[i] = (char) (i + 65);
            shortArray[i] = (short) (i + 10);
            shortArrayObj[i] = (short) (i + 10);
            intArray[i] = i + 100;
            intArrayObj[i] = i + 100;
            longArray[i] = i + 1000;
            longArrayObj[i] = (long) (i + 1000);
            floatArray[i] = (float) (i + 0.5);
            floatArrayObj[i] = (float) (i + 0.5);
            doubleArray[i] = i + 0.123;
            doubleArrayObj[i] = i + 0.123;
            objectArray[i] = new Object();
            stringArray[i] = "Element " + (i + 1);
        }

       
        System.out.println("byteArray: " + Arrays.toString(byteArray));
        System.out.println("byteArrayObj: " + Arrays.toString(byteArrayObj));
        System.out.println("charArray: " + Arrays.toString(charArray));
        System.out.println("charArrayObj: " + Arrays.toString(charArrayObj));
        System.out.println("shortArray: " + Arrays.toString(shortArray));
        System.out.println("shortArrayObj: " + Arrays.toString(shortArrayObj));
        System.out.println("intArray: " + Arrays.toString(intArray));
        System.out.println("intArrayObj: " + Arrays.toString(intArrayObj));
        System.out.println("longArray: " + Arrays.toString(longArray));
        System.out.println("longArrayObj: " + Arrays.toString(longArrayObj));
        System.out.println("floatArray: " + Arrays.toString(floatArray));
        System.out.println("floatArrayObj: " + Arrays.toString(floatArrayObj));
        System.out.println("doubleArray: " + Arrays.toString(doubleArray));
        System.out.println("doubleArrayObj: " + Arrays.toString(doubleArrayObj));
        System.out.println("objectArray: " + Arrays.toString(objectArray));
        System.out.println("stringArray: " + Arrays.toString(stringArray));

      
        String[] dataStructs = {"Listas", "Colas", "Pilas", "Mapas", "Conjuntos"};
        String[] características = {"Simple", "Circular", "Enlazada", "Primero en entrar, Primero en salir", "Primero en entrar, Último en salir", "Parejas de clave y valor", "Elementos no repetidos"};

        
        Scanner scanner = new Scanner(System.in);
        String[] inputArray = new String[5];
        for (int i = 0; i < 5; i++) {
            System.out.print("Ingrese un dato: ");
            inputArray[i] = scanner.nextLine();
        }

       
        System.out.println("\nElementos del arreglo dataStructs con su equivalente elemento del arreglo características:");
        for (int i = 0; i < dataStructs.length; i++) {
            System.out.println(dataStructs[i] + " - " + características[i]);
        }

        
        int[] ventas = new int[(int) (Math.random() * 10) + 1]; // (1 to 10)
        for (int i = 0; i < ventas.length; i++) {
            ventas[i] = (int) (Math.random() * 1000) + 1; // (1 to 1000)
        }

       
        System.out.println("\nCantidad de ventas: " + ventas.length);

        
        System.out.println("Valor de cada venta: " + Arrays.toString(ventas));

        
        int totalVentas = 0;
        for (int venta : ventas) {
            totalVentas += venta;
        }
        System.out.println("Total de ventas: " + totalVentas);

        
        double promedioVentas = (double) totalVentas / ventas.length;
        System.out.println("Promedio de ventas: " + promedioVentas);

        
        int ventaMasAlta = buscarVentaMasAlta(ventas);
        System.out.println("\nVenta más alta: " + ventaMasAlta);

      
        int ventaMasBaja = buscarVentaMasBaja(ventas);
        System.out.println("Venta más baja: " + ventaMasBaja);

       
        System.out.println("Total de ventas (usando función): " + obtenerTotalVentas(ventas));

       
        System.out.println("Promedio de ventas (usando función): " + obtenerPromedioVentas(ventas));

       
        int ventaCercanaPromedio = obtenerVentaCercanaPromedio(ventas, promedioVentas);
        System.out.println("Venta más cercana al promedio: " + ventaCercanaPromedio);

      
        ordenarVentasDescendente(ventas);
        System.out.println("\nVentas ordenadas de forma descendente: " + Arrays.toString(ventas));

     
        ordenarVentasAscendente(ventas);
        System.out.println("Ventas ordenadas de forma ascendente: " + Arrays.toString(ventas));

       
        desordenarVentas(ventas);
        System.out.println("Ventas desordenadas: " + Arrays.toString(ventas));

        
        ordenarVentasPartesImpares(ventas);
        System.out.println("Ventas ordenadas primero las pares y luego las impares: " + Arrays.toString(ventas));


        Object[][] lenguajes = new Object[5][5];
        lenguajes[0] = new Object[]{"NOMBRE", "AÑO", "AUTOR", "DETALLES", "FRAMEWORKS"};

        
        infoLenguajes(lenguajes, inputArray);

    }

    
    public static int buscarVentaMasAlta(int[] ventas) {
        int ventaMaxima = Integer.MIN_VALUE;
        for (int venta : ventas) {
            if (venta > ventaMaxima) {
                ventaMaxima = venta;
            }
        }
        return ventaMaxima;
    }

    
    public static int buscarVentaMasBaja(int[] ventas) {
        int ventaMinima = Integer.MAX_VALUE;
        for (int venta : ventas) {
            if (venta < ventaMinima) {
                ventaMinima = venta;
            }
        }
        return ventaMinima;
    }

    
    public static int obtenerTotalVentas(int[] ventas) {
        int totalVentas = 0;
        for (int venta : ventas) {
            totalVentas += venta;
        }
        return totalVentas;
    }

    
    public static double obtenerPromedioVentas(int[] ventas) {
        return (double) obtenerTotalVentas(ventas) / ventas.length;
    }

    
    public static int obtenerVentaCercanaPromedio(int[] ventas, double promedio) {
        int ventaCercana = ventas[0];
        double minDistancia = Math.abs(ventas[0] - promedio);
        for (int venta : ventas) {
            double distancia = Math.abs(venta - promedio);
            if (distancia < minDistancia) {
                minDistancia = distancia;
                ventaCercana = venta;
            }
        }
        return ventaCercana;
    }

    
    public static void ordenarVentasDescendente(int[] ventas) {
        Arrays.sort(ventas);
        for (int i = 0; i < ventas.length / 2; i++) {
            int temp = ventas[i];
            ventas[i] = ventas[ventas.length - 1 - i];
            ventas[ventas.length - 1 - i] = temp;
        }
    }

    
    public static void ordenarVentasAscendente(int[] ventas) {
        Arrays.sort(ventas);
    }

    
    public static void desordenarVentas(int[] ventas) {
        for (int i = 0; i < ventas.length; i++) {
            int randIndex = (int) (Math.random() * ventas.length);
            int temp = ventas[i];
            ventas[i] = ventas[randIndex];
            ventas[randIndex] = temp;
        }
    }

  
    
    public static void ordenarVentasPartesImpares(int[] ventas) {
        Arrays.sort(ventas, 0, ventas.length / 2);
        Arrays.sort(ventas, ventas.length / 2, ventas.length);
    }

    
   
    public static void infoLenguajes(Object[][] lenguajes, String[] inputArray) {
        try (Scanner scanner = new Scanner(System.in)) {
            for (int i = 1; i < lenguajes.length; i++) {
                for (int j = 0; j < lenguajes[i].length; j++) {
                    if (j < inputArray.length) {
                        lenguajes[i][j] = inputArray[j];
                    } else {
                        System.out.print("Ingrese un dato para la posición [" + i + "][" + j + "]: ");
                        lenguajes[i][j] = scanner.nextLine();
                    }
                }
            }
        }
    }
}
