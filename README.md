# XamarinForms-NETStandard-1.4-Project-Templates

Reference:

1. http://blog.kkbruce.net/2016/12/xamarin-pcl-upgrade-to-net-standard-library.html
2. http://blog.kkbruce.net/2016/12/xamarin-forms-droid-ios-upgrade-nuget-v3-project-json.html
3. http://blog.kkbruce.net/2016/12/custome-solution-template-with-multiple-projects.html

Make Xamarin.Forms - Blank App (Xamarin.Forms Portable) for .NET Standard 1.4 Project Templates.

You can direct download [Templates](https://github.com/kkbruce/Xamarin.Forms-.NETStandard-Project-Templates/tree/master/Templates) files to your Visual Studio project template location, defualt location is "C:\Users\\{username}\Documents\Visual Studio 2015\Templates\ProjectTemplates".

## Notes

This project template is use Export Template function to make it, but **multiple projects** have some issue you must **manual** fix it:

1. Droid project &rarr; MainActivity.cs 

`[Activity(Label = "tryNETStandard", Icon = "@drawable/icon", Theme = "@style/MainTheme", MainLauncher = true, ConfigurationChanges = ConfigChanges.ScreenSize | ConfigChanges.Orientation)]`

The `Label` value replace to PCL namespace.

2. UWP project &rarr; MainPage.xaml.cs

`LoadApplication(new tryNETStandard.App());`

Replace string "tryNETStandard" to PCL namespace.

3. All platform projects remove tryNETStandard reference from References, re-reference your Portable project.

if you can't see NETStandard.Library in your PCL project,  Rebuild and restar solution.