```java  
        BigDecimal f=new BigDecimal("2");
        f=f.multiply(new BigDecimal(100));
        System.out.println(f.intValue());  //200

        BigDecimal se=new BigDecimal("4.7");
        se=se.multiply(new BigDecimal(10));
        System.out.println(se.intValue());//47

        BigDecimal to =f.multiply(se);
        System.out.println(to.intValue());//9400

        BigDecimal temp= new BigDecimal(100);
        System.out.println(temp.subtract(se).intValue());//53
        BigDecimal tof=f.multiply(temp.subtract(se));
        System.out.println(tof.intValue());


        String toActul=formatTwoRMB(to.intValue()/10000d);
        System.out.println(toActul);


        tof=new BigDecimal("1205");
        String toNotActul=formatTwoRMB(tof.intValue()/1000d);

        System.out.println(tof.intValue()/1000d);

        System.out.println(toNotActul);


        Double a=1.0560232;
        System.out.println(Math.round(a*100 + 0.5)/100.0);

        Double value= new BigDecimal(a).setScale(2,java.math.BigDecimal.ROUND_HALF_UP).doubleValue();

        System.out.println(value);
```

