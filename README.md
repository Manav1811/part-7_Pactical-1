# part-7_Pactical-1

package part7;

public class Practical_1 {

	public static void main(String[] args) {
		// Create an Integer array
		Integer[] intArray = { 2, new Integer(4), new Integer(3), new Integer(5) }; // Autoboxing is done

		Double[] doubleArray = { new Double(3.4), new Double(10.3), new Double(-20.1), new Double(9.78), 5.7 };
		Character[] charArray = { new Character('F'), new Character('O'), new Character('O'), new Character('T') };
		Float[] floatArray = { new Float(1.2f), new Float(10.4f), new Float(3.7f), new Float(-20.6f) };
		String[] stringArray = { "myself", "foot", "Hello" };

		sort(intArray);
		sort(doubleArray);
		sort(charArray);
		sort(stringArray);
		sort(floatArray);
		System.out.print("Sorted Integer objects: ");
		printList(intArray);
		System.out.print("Sorted Double objects: ");
		printList(doubleArray);
		System.out.print("Sorted Character objects: ");
		printList(charArray);
		System.out.print("Sorted String objects: ");
		printList(stringArray);
		System.out.print("Sorted Float objects: ");
		printList(floatArray);
		System.out.println("This is created by 21CE063_Manav Luhar.");
	}

	public static <T extends Comparable<T>> void sort(T[] list) {
		T currentMin = null;
		int currentMinIndex;
		for (int i = 0; i < list.length - 1; i++) {

			currentMin = list[i];
			currentMinIndex = i;
			for (int j = i + 1; j < list.length; j++) {
				if (currentMin.compareTo(list[j]) > 0) {
					currentMin = list[j];
					currentMinIndex = j;
				}
			}

			if (currentMinIndex != i) {
				list[currentMinIndex] = list[i];
				list[i] = currentMin;
			}
		}
	}

	public static void printList(Object[] list) {
		
		for (int i = 0; i < list.length; i++) 
		{
			System.out.print(list[i] + " ");
		}
		
		System.out.println();
		
	}
	
	
	
}
