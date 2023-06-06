## Including WinForm Control in WPF

### Code Behind

You can use the control ElementHost that resides in the namespace System.Windows.Forms.Integration to host a WPF-Usercontrol in WinForms. This control has a property called Child to which you can assign an instance of an UIElement1.

Here is an example of how to use ElementHost control to place a WPF UIElement on your Windows Forms control or form2:

```c#
private void Form1_Load(object sender, EventArgs e) 
{ 
    // Create the ElementHost control for hosting the WPF UserControl. 
    ElementHost host = new ElementHost(); 
    host.Dock = DockStyle.Fill; 

    // Create the WPF UserControl. 
    MyWpfUserControl myWpfControl = new MyWpfUserControl(); 

    // Assign the WPF UserControl to the ElementHost control's Child property. 
    host.Child = myWpfControl; 

    // Add the ElementHost control to the form's controls collection. 
    this.Controls.Add(host); 
}
```

### XAML

```xaml
<Window x:Class="WpfApplication1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"
        Title="MainWindow" Height="350" Width="525">
    <Grid>
        <WindowsFormsHost>
            <wf:ElementHost x:Name="elementHost" DockPanel.Dock="Top"/>
        </WindowsFormsHost>
    </Grid>
</Window>
```

## Enabling Control on TAB

```xaml
<Window x:Class="WpfApplication1.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        Title="MainWindow" Height="350" Width="525">
    <Grid>
        <TabControl>
            <TabItem Header="Tab 1">
                <local:UserControl1/>
            </TabItem>
            <TabItem Header="Tab 2">
                <local:UserControl2/>
            </TabItem>
        </TabControl>
    </Grid>
</Window>
```


