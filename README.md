--------------
      BigDecimal.setScale()方法用于格式化小数点
      setScale(1)表示保留一位小数，默认用四舍五入方式 
      setScale(1,BigDecimal.ROUND_DOWN)直接删除多余的小数位，如2.35会变成2.3 
      setScale(1,BigDecimal.ROUND_UP)进位处理，2.35变成2.4 
      setScale(1,BigDecimal.ROUND_HALF_UP)四舍五入，2.35变成2.4
      setScaler(1,BigDecimal.ROUND_HALF_DOWN)四舍五入，2.35变成2.3，如果是5则向下舍
---------
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
        System.out.println(tof.intValue());//10600


        String toActul=formatTwoRMB(to.intValue()/10000d);
        System.out.println(toActul); //0.94


        tof=new BigDecimal("1205");
        String toNotActul=formatTwoRMB(tof.intValue()/1000d);

        System.out.println(tof.intValue()/1000d);// 1.205

        System.out.println(toNotActul);//1.21


        Double a=1.0560232;
        System.out.println(Math.round(a*100 + 0.5)/100.0);//1.06

        Double value= new BigDecimal(a).setScale(2,java.math.BigDecimal.ROUND_HALF_UP).doubleValue();

        System.out.println(value);//1.06
```

1.205
