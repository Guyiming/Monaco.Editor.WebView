# Monaco.Editor.WebView
Monaco Editor based on WebView2, for desktop use, such as WPF, WinForm.
> Only packaged the Monaco Editor min folder.


|NuGet |
|--|
|[![](https://img.shields.io/nuget/v/monaco.editor.webview.svg)](https://www.nuget.org/packages/Monaco.Editor.WebView)|

# How to use
Add a `WebView2` control:
```xaml
<Grid>
    <web:WebView2 xmlns:web="clr-namespace:Microsoft.Web.WebView2.Wpf;assembly=Microsoft.Web.WebView2.Wpf"
                  x:Name="webView21" HorizontalAlignment="Stretch" VerticalAlignment="Stretch"/>
</Grid>
```
write some code
```csharp
private void MainWindow_Loaded(object sender, RoutedEventArgs e)
{
    this.webView21.Source = new Uri(System.IO.Path.Combine(AppDomain.CurrentDomain.BaseDirectory,@"Monaco\index.html"));
    this.webView21.NavigationCompleted += WebView21_NavigationCompleted;
}
private void WebView21_NavigationCompleted(object? sender, CoreWebView2NavigationCompletedEventArgs e)
{
    webView21.ExecuteScriptAsync("editor.setValue('public class Test{}');");
}
```
after the 'NavigationCompleted' you can call the `editor` relate function.

<img width="1175" height="666" alt="image" src="https://github.com/user-attachments/assets/716d2bab-cf72-41bf-b6b6-1cb4c2d471e3" />
