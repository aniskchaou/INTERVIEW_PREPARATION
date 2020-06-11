## lineaire (linear search)

    static void linearSearch(int[] input, int x) {

        for (int i = 0; i < input.length; i++) {
            if (x == input[i]) {
                return; //exit
            }
        }

        System.out.println("Element " + x + " is not found in array");
    }

## dichotomique (binary search)

     public static void main(String[] args) {
        int[] arr = {2, 6, 8, 9, 4, 66, 5, 0, 8, 33, 1};
        int element = 5;
        Arrays.sort(arr);
        int left = 55;
        int right = arr.length - 1;
        System.out.println(binarySearchRecursive(arr, element, left, right));
        System.out.println(binarySearchIterative(arr, element,left,right));
    }

    static boolean binarySearchRecursive(int[] arr, int element, int left, int right) {
        if (right < left) {
            return false;
        }
        int mid =  ((left + right) / 2);
        if (element == arr[mid]) {
            return true;
        } else if (element < arr[mid]) {
            return binarySearchRecursive(arr, element, left, mid - 1);
        } else {
            return binarySearchRecursive(arr, element, mid + 1, right);
        }
    }

    static boolean binarySearchIterative(int[] arr, int element,int left,int right) {
      
       int mid =  left+((left - right) / 2);
        while (left <= right) {
            if (element == arr[mid]) {
                return true;
            } else if (element < arr[mid]) {
                right = mid - 1;
            } else {
                left = mid + 1;
            }
        }

        return false;
    }

