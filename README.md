# XFCustomProgressBar
NuGet source of custom progress bar

Easy customised progress bar with :

SolidColorBrush
RadialGradientBrush
LinearGradientBrush
Customised properties:

HeightRequest and CornerRadius

Start and End colours for brushes; Text font and Text colors of percentage label; Funny fill process bar animation 😃

Just add reference:  xmlns:customControls="clr-namespace:CustomProgressBar.Controls;"

<?xml version="1.0" encoding="utf-8" ?>
<ContentPage xmlns="http://xamarin.com/schemas/2014/forms"
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             xmlns:customControls="clr-namespace:CustomProgressBar.Controls;"
             BackgroundColor="White"
             x:Class="CustomProgressBar.Pages.MainPage">

    <StackLayout
        Padding="20,40">
        <Frame
            BackgroundColor="#2196F3"
            Padding="24"
            CornerRadius="0">

            <Label
                Text="Welcome to Xamarin.Forms!"
                HorizontalTextAlignment="Center"
                TextColor="White"
                FontSize="36"/>
        </Frame>
        
        <customControls:CustomProgressBar
            Margin="10"
            BorderColor="LightBlue"
            HeightRequest="30"
            StartColor="#40E0D0"
            StopColor="#CCCCFF"
            BrushRadius="0.36"
            ProgressFontSize="18"
            CornerRadius="10"
            Progress="{Binding Progress}"
            ProgressTextColor="Black"
            EmptyAreaColor="#EAF2F8"
            BackgroudBrush="{Binding SelectedBrush}"
            x:Name="customControl"/>

        <Picker
            VerticalOptions="EndAndExpand"
            HorizontalOptions="Center"
            Title="Select picker brush type"
            BackgroundColor="#2874A6"
            TextColor="White"
            TitleColor="White"
            HeightRequest="40"
            HorizontalTextAlignment="Center"
            ItemsSource="{Binding BrushTypesList}"
            SelectedIndex="4"
            SelectedItem="{Binding SelectedBrush}"/>

        <Button
            Text="Let's make progress!"
            Margin="10"
            HeightRequest="40"
            BackgroundColor="#2874A6"
            Command="{Binding MakeProgressCommand}"
            TextColor="White">
        </Button>

    </StackLayout>

</ContentPage>
