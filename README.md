# OpenCV 3.4.0 Java project configuration on Windows with Intellij IDEA

Add DLLs to Path  
![title Windows Path](https://github.com/chegel/OpenCV-3.4.0-windows-x64/blob/master/images/Windows_Path.jpg)  
Add jar file to project lib folder  
Add Native Library Locations folder with DLLs  
![title IDEA libraries](https://github.com/chegel/OpenCV-3.4.0-windows-x64/blob/master/images/IDEA_libraries.jpg)  

Maven  

```
<dependency>
	<groupId>org.opencv</groupId>
	<artifactId>opencv</artifactId>
	<version>3.4.0</version>
	<scope>system</scope>
	<systemPath>${project.basedir}/lib/opencv-340.jar</systemPath>
</dependency>
```

In Java class load native library  

```
static{
	System.loadLibrary(Core.NATIVE_LIBRARY_NAME); // load opencv_java
}
```

opencv-340.jar contents  
![title jar contants](https://github.com/chegel/OpenCV-3.4.0-windows-x64/blob/master/images/jar.jpg)  

Code sample  

```java
import org.opencv.core.Mat;
import org.opencv.core.MatOfByte;
import org.opencv.imgcodecs.Imgcodecs;
...
Mat rawFaceImage = Imgcodecs.imdecode(new MatOfByte(rawImage), Imgcodecs.CV_LOAD_IMAGE_COLOR);
...
Imgproc.cvtColor(frame, grayFrame, Imgproc.COLOR_BGR2GRAY);
```