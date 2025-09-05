# binding-selected-items-in-.net-maui-treeview
This repository demonstrates how to bind and manage selected items in the .NET MAUI TreeView (SfTreeView) control. It provides a sample implementation showing how to synchronize the selection state between the TreeView and the ViewModel, enabling multiple selection and real-time updates through data binding.

## Sample

### XAML

```xaml
    <syncfusion:SfTreeView x:Name="treeView"
                            SelectionMode="Multiple"
                            ChildPropertyName="States" 
                            ItemsSource="{Binding CountriesInfo}"
                            SelectedItems="{Binding SelectedCountries}"
                            AutoExpandMode="RootNodesExpanded">
    </syncfusion:SfTreeView>
</ContentPage.Content>
```

### View Model

```csharp
public class CountriesViewModel
{
    public CountriesViewModel()
    {
        GenerateCountriesModelModelInfo();
    }
    public ObservableCollection<CountriesModel> CountriesInfo { get; set; }

    public ObservableCollection<object> SelectedCountries { get; set; }

    private void GenerateCountriesModelModelInfo()
    {
        this.CountriesInfo = new ObservableCollection<CountriesModel>();
        CountriesInfo.Add(australia);
        CountriesInfo.Add(brazil);
        CountriesInfo.Add(china);
        CountriesInfo.Add(usa);
        CountriesInfo.Add(india);

        SelectedCountries = new ObservableCollection<object>();
        SelectedCountries.Add(nsw);
        SelectedCountries.Add(california);
        SelectedCountries.Add(victoria);
        SelectedCountries.Add(india);
        SelectedCountries.Add(china);
    }
}
```

## Requirements to run the demo

To run the demo, refer to [System Requirements for .NET MAUI](https://help.syncfusion.com/maui/system-requirements).

Make sure that you have the compatible versions of [Visual Studio 2022](https://visualstudio.microsoft.com/downloads/ ) with the Dot NET MAUI workload and [.NET Core SDK 7.0](https://dotnet.microsoft.com/en-us/download/dotnet/7.0) or later version in your machine before starting to work on this project.

## Troubleshooting:
### Path too long exception

If you are facing path too long exception when building this example project, close Visual Studio and rename the repository to short and build the project.

## License

Syncfusion® has no liability for any damage or consequence that may arise from using or viewing the samples. The samples are for demonstrative purposes. If you choose to use or access the samples, you agree to not hold Syncfusion® liable, in any form, for any damage related to use, for accessing, or viewing the samples. By accessing, viewing, or seeing the samples, you acknowledge and agree Syncfusion®'s samples will not allow you seek injunctive relief in any form for any claim related to the sample. If you do not agree to this, do not view, access, utilize, or otherwise do anything with Syncfusion®'s samples.