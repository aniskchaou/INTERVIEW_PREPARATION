  ## Approximation Pi

        double Pi = 0.0;
        long start = System.currentTimeMillis();
        for (double i = 1; i < 100000000; i++) {
            Pi += (i % 2 == 0) ? -1 / (2 * i - 1) : 1 / (2 * i - 1);
        }
        long stop = System.currentTimeMillis();
        System.out.println(Pi * 4);
        System.out.println(Math.PI);
        System.out.println(stop-start+" ms");

## output

    // 3.141592663589326
    // 3.141592653589793
    // 2426 ms
