<Window x:Class="WpfApp3.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp3"
        mc:Ignorable="d"
        Title="Dodaj pracownika" Height="450" Width="800">
    <Grid Background="LightSteelBlue">
        <GroupBox Header="Dane pracownika" Margin="51,160,446,72">
            <StackPanel>

                <Label Content="Imię:" HorizontalAlignment="Left"/>
                <TextBox x:Name="imie_txt" TextWrapping="Wrap" Width="120" HorizontalAlignment="Left" VerticalAlignment="Top"/>
                <Label Content="Nazwisko:" HorizontalAlignment="Left"/>
                <TextBox x:Name="nazwisko_txt" TextWrapping="Wrap" Width="120" HorizontalAlignment="Left"/>
                <Label Content="Stanowisko:" HorizontalAlignment="Left"/>
                <ComboBox x:Name="Stanowisko_combo" Width="120" HorizontalAlignment="Left">
                    <ListBoxItem Content="Kierownik"/>
                    <ListBoxItem Content="Starszy programista"/>
                    <ListBoxItem Content="Młodszy programista"/>
                    <ListBoxItem Content="Tester"/>
                </ComboBox>

            </StackPanel>
        </GroupBox>
        <GroupBox Header="Generowanie hasła" Margin="477,160,18,72">
            <StackPanel>
                <Label Content="Ile znaków?" HorizontalAlignment="Left"/>
                <TextBox x:Name="ileznaow_txt" TextWrapping="Wrap" Text="" Width="120" HorizontalAlignment="Left"/>
                <CheckBox x:Name="malelitery_check" Content="Małe i wielkie litery" HorizontalAlignment="Left"/>
                <CheckBox x:Name="cyfry_check" Content="Cyfry" HorizontalAlignment="Left"/>
                <CheckBox x:Name="specjalne_check" Content="Znaki specjalne" HorizontalAlignment="Left"/>
                <Button x:Name="generuj_btn" Content="Generuj hasło" Width="110" Background="SteelBlue" Click="generuj_btn_Click"/>


            </StackPanel>
        </GroupBox>
        <Button x:Name="Zatwierdź_btn" Content="Zatwierdź"  Background="SteelBlue" HorizontalAlignment="Center" Margin="0,392,0,0" VerticalAlignment="Top" Width="154" Click="Zatwierdź_btn_Click"/>

    </Grid>
</Window>
