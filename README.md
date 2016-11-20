# android-custom-junit-report
A customized Junit TestRunner for android Activity automation .

Instrcutions to use:

1> Run builld.xml inside with "ant clean jar" to create runner jar (which is already added)  inside the "build" folder .
2> Place that jar inside "robot-calc/libs" folder .
3> Inside "robot-calc/AndroidManifest.xml"  change the below line 

 <instrumentation
        android:name="android.test.InstrumentationTestRunner"
        android:targetPackage="com.calculator" />
        
        from 
        
         <instrumentation
        android:name="com.custom.android.junitreport.JUnitReportTestRunner"
        android:targetPackage="com.calculator" />
        
        

4> While running the "robot-calc" automation with  custom made testRunner , type below
adb shell am instrument -w com.calculator.test/com.custom.android.junitreport.JUnitReportTestRunner

-----------------------------------------------------------------------------------------------------


It will create a Junit xml report of the junit3 tests for "robot-calc/src/com/calculator/test/MainActivityTest.java"
 inside "/sdcard/testReports" folder of your android device .



