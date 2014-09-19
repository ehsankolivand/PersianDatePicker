PersianDatePicker
=================

An Android DatePicker for Persian Calendar

Usage:

1- Add as an Android Library Project:<br/>
Add this library project to your project. In your layout file:

1-1- Add this line to root layout element:<br/>
xmlns:persianDatePicker="http://schemas.android.com/apk/res-auto"

1-2- Add PersianDatePicker view:<br/>
    <ir.smartlab.persindatepicker.PersianDatePicker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>
        
2- Add Source and other required things to your Project:<br/>
2-1- Copy all sources to your source tree.<br/>
2-2- Copy /res/layout/sl_persian_date_picker.xml to your /res/layout folder.<br/>
2-3- Add this to your /res/values/attrs.xml:<br/>
    <declare-styleable name="PersianDatePicker">
        <attr name="minYear" format="integer" />
        <attr name="maxYear" format="integer" />
        <attr name="selectedYear" format="integer" />
        <attr name="selectedMonth" format="integer" />
        <attr name="selectedDay" format="integer" />
        <attr name="displayMonthNames" format="boolean" />
        <attr name="yearRange" format="integer" />
    </declare-styleable>
    
Params:<br/>
1- minYear: Min value for year in the picker. Default is current Hijri Shamsi (Jalali) year - yearRange(default is 10).<br/>
2- maxYear: Max value for year in the picker. Default is current Hijri Shamsi (Jalali) year + yearRange(default is 10).<br/>
3- yearRange: If you set a selected year, available years in picker will be from (selectedYear - yearRange) to (selectedYear + yearRange). Default value is 10.<br/>
4- selectedYear: Selected year that PersianDatePicker starts with. Default is the current Hijri Shamsi (Jalali) year.<br/>
5- selectedMonth: Selected month that PersianDatePicker starts with. Default is the current Hijri Shamsi (Jalali) year's month.<br/>
6- selectedDay: Selected day of month that PersianDatePicker starts with. Default is the current Hijri Shamsi (Jalali) month's day. <br/>
7- displayMonthNames: If set to true, months names are displayed, otherwise their number will be shown.<br/>

Example:<br/>
1- Display a PersianDatePicker with current Hijri Shamsi (Jalali) values:<br/>
    <ir.smartlab.persindatepicker.PersianDatePicker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"/>
        
2- Display a PersianDatePicker with selected Hijri Shamsi (Jalali) date:<br/>
    <ir.smartlab.persindatepicker.PersianDatePicker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:selectedYear="1390"
        app:selectedMonth="5"
        app:selectedDay="15" />
  
3- Display a PersianDatePicker that shows month names:<br/>
    <ir.smartlab.persindatepicker.PersianDatePicker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:displayMonthNames="true" />
        
4- Display a PersianDatePicker that shows years between 1350 and 1450:<br/>
    <ir.smartlab.persindatepicker.PersianDatePicker
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:maxYear="1450"
        app:minYear="1350" />
        
Java code:<br/>
1- You can set a java.util.Date object to PersianDatePpicker in java code:<br/>
    persianDatePicker.setDisplayDate(new Date());
    
2- you can also set a ir.smartlab.persindatepicker.util.PersianCalendar object:<br/>
    PersianCalendar persianCalendar = new PersianCalendar();
    persianCalendar.setPersianDate(1393, 6, 28);
    persianDatePicker.setDisplayPersianDate(persianCalendar);
		
3- You can get displayed date in java.util.Date or ir.smartlab.persindatepicker.util.PersianCalendar:<br/>
    Date d = persianDatePicker.getDisplayDate();<br/>
    or<br/>
    PersianCalendar pCal = persianDatePicker.getDisplayPersianDate();<br/>

Leap Year:<br/>
In Hijri Shamsi some years are leap year, so the last month of year is 30 days (not 29 days). <br/>
PersianDatePicker take cares of leap years. This means that users will never pick a wrong date.<br/>

Credits:<br/>
PersianDatepicker is heavily based on AOSP (https://source.android.com) and PersianCalendar (http://sourceforge.net/projects/persiancalendar).

