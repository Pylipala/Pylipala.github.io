大小写敏感不一样也是不一样
=======
`SimpleDateFormat`在Mac和Android模拟器里面对毫秒的标记大小写敏感不一样。
在Mac上，`yyyy-MM-dd HH:mm:ss.sss`和`yyyy-MM-dd HH:mm:ss.SSS`都工作，但是在Android模拟器上，小写的`sss`那个就不工作了。
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;

public class Main {

    public static void main(String[] args) throws ParseException {
        SimpleDateFormat simpleDateFormat = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.sss");
        SimpleDateFormat simpleDateFormat2 = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.SSS");

        Date date = new Date();

        toStringThenParse(simpleDateFormat, date);
        toStringThenParse(simpleDateFormat2, date);
    }

    public static void toStringThenParse(SimpleDateFormat dateFormat, Date date) throws ParseException {
        String formatString = dateFormat.format(date);
        System.out.println("Format String: " + formatString);
        Date parsedDate = dateFormat.parse(formatString);
        System.out.println("Format->Parsed->Format: " + dateFormat.format(parsedDate));
    }
}
```

Mac上的输出
```
Format String: 2014-08-24 16:02:56.056
Format->Parsed->Format: 2014-08-24 16:02:56.056
Format String: 2014-08-24 16:02:56.272
Format->Parsed->Format: 2014-08-24 16:02:56.272
```
模拟器上的输出
```
08-24 16:05:00.831    2019-2032/? I/System.out﹕ Format String: 2014-08-24 16:05:00.000
08-24 16:05:00.831    2019-2032/? I/System.out﹕ Format->Parsed->Format: 2014-08-24 16:05:00.000
08-24 16:05:00.841    2019-2032/? I/System.out﹕ Format String: 2014-08-24 16:05:00.842
08-24 16:05:00.841    2019-2032/? I/System.out﹕ Format->Parsed->Format: 2014-08-24 16:05:00.842
```

不积跬步，无以至千里
