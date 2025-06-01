# How to Add Arrows to the Chart Axis in WPF Chart
This article provides a detailed walkthrough on how to add arrows to the axis using Annotations in [WPF Chart](https://www.syncfusion.com/wpf-controls/charts).

The [SfChart](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html) includes support for [Annotations](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.SfChart.html#Syncfusion_UI_Xaml_Charts_SfChart_Annotations), enabling the addition of various types of annotations to enhance chart visualization. Using [Line Annotation](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.LineAnnotation.html) for you can achieves to add arrows to the axis.

The Line Annotation includes following property:
* [X1](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_X1) - Represents the X1 Coordinate of the Line Annotation.
* [X2](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_X2) - Represents the X2 Coordinate of the Line Annotation.
* [Y1](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_Y1) - Represents the Y1 Coordinate of the Line Annotation.
* [Y2](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_Y2) - Represents the Y2 Coordinate of the Line Annotation.
* [CanDrag](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanDrag) - A Boolean value that represent to drag the Annotation.
* [CanResize](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.ShapeAnnotation.html#Syncfusion_UI_Xaml_Charts_ShapeAnnotation_CanResize) - A Boolean value that represent to resize the Annotation.
* [CoordinateUnit](https://help.syncfusion.com/cr/wpf/Syncfusion.UI.Xaml.Charts.Annotation.html#Syncfusion_UI_Xaml_Charts_Annotation_CoordinateUnit) - A Coordinate unit value that represent to position the Annotation.

Learn step-by-step instructions and gain insights to add arrows to the axis using annotations.

**Step 1:** Initialize the SfChart and add the series and legend to it as follows.

**XAML**
 
 ```xml
<chart:SfChart>
    
    <chart:SfChart.Legend>
        <chart:ChartLegend/>
    </chart:SfChart.Legend>

    <chart:ColumnSeries ItemsSource="{Binding ElectronicsSales}"
                    XBindingPath="Month"
                    YBindingPath="Sales"
                    ShowTooltip="True"
                    EnableAnimation="True"
                    Label="Electronic Sales">
    </chart:ColumnSeries>

    <chart:ColumnSeries ItemsSource="{Binding FurnitureSales}"
                    XBindingPath="Month"
                    YBindingPath="Sales"
                    ShowTooltip="True"
                    EnableAnimation="True"
                    Label="Furniture Sales">
    </chart:ColumnSeries>

</chart:SfChart> 
 ```

 
**Step 2:** Initialize the LineAnnotation within the Annotations collection of the SfChart, configure it to align with the desired axis, and use the LineCap property to add arrows to the line annotation.

**XAML**
 
 ```xml
<chart:SfChart>
    
    <chart:SfChart.PrimaryAxis>
        <chart:CategoryAxis EdgeLabelsDrawingMode="Fit" Header="Months" PlotOffsetEnd="15">
            ......
        </chart:CategoryAxis>
    </chart:SfChart.PrimaryAxis>

    <chart:SfChart.SecondaryAxis>
        <chart:NumericalAxis Minimum="0" Maximum="30000" Interval="10000" Header="Sales Rate" PlotOffsetEnd="5" PlotOffsetStart="5">
            ......
        </chart:NumericalAxis>
    </chart:SfChart.SecondaryAxis>

    <chart:SfChart.Legend>
        <chart:ChartLegend/>
    </chart:SfChart.Legend>

    <chart:SfChart.Annotations>
        <chart:LineAnnotation CoordinateUnit="Axis" X1="-0.5" X2="5.6" Y1="0" Y2="0" Stroke="Black" LineCap="Arrow" CanDrag="True" CanResize="True"/>
        <chart:LineAnnotation CoordinateUnit="Axis" X1="-0.5" X2="-0.5" Y1="0" Y2="30000" Stroke="Black" LineCap="Arrow" CanDrag="True" CanResize="True"/>
    </chart:SfChart.Annotations>

</chart:SfChart> 
 ```
 

**Output:**

![AddArrowToAnnotation](https://github.com/user-attachments/assets/2ab333c7-3f49-4b98-a15e-71679a1ef332)

#### Path too long exception

If you are facing a path too long exception when building this example project, close Visual Studio and rename the repository to a shorter name before building the project.

For more details, refer to the KB on [how to add arrows to the chart axis in WPF Chart](https://support.syncfusion.com/kb/article/18304/how-to-add-arrows-to-the-chart-axis-in-wpf-chart).
