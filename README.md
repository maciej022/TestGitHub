using System;
using System.Text;
using System.Windows;

namespace WpfApp3
{
    public partial class MainWindow : Window
    {
        private string maleDuzeLitery = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
        private string cyfry = "1234567890";
        private string znakiSpecjalne = "!@#$%^&*";
        private Random losuj = new Random();

        public MainWindow()
        {
            InitializeComponent();
        }

        private void generuj_btn_Click(object sender, RoutedEventArgs e)
        {
            if (!int.TryParse(ileznakow_txt.Text, out int dlugoscHasla) || dlugoscHasla <= 0)
            {
                MessageBox.Show("Podaj poprawną liczbę znaków!", "Błąd", MessageBoxButton.OK, MessageBoxImage.Warning);
                return;
            }

            string dozwoloneZnaki = "";

            if (malelitery_check.IsChecked == true)
                dozwoloneZnaki += maleDuzeLitery;

            if (cyfry_check.IsChecked == true)
                dozwoloneZnaki += cyfry;

            if (specjalne_check.IsChecked == true)
                dozwoloneZnaki += znakiSpecjalne;

            if (string.IsNullOrEmpty(dozwoloneZnaki))
            {
                MessageBox.Show("Wybierz co najmniej jeden typ znaków!", "Błąd", MessageBoxButton.OK, MessageBoxImage.Warning);
                return;
            }

            StringBuilder haslo = new StringBuilder();

            for (int i = 0; i < dlugoscHasla; i++)
            {
                int index = losuj.Next(dozwoloneZnaki.Length);
                haslo.Append(dozwoloneZnaki[index]);
            }

            MessageBox.Show($"Wygenerowane hasło: {haslo}", "Hasło", MessageBoxButton.OK, MessageBoxImage.Information);
        }

        private void Zatwierdź_btn_Click(object sender, RoutedEventArgs e)
        {
            string stanowisko = Stanowisko_combo.SelectedItem is ComboBoxItem selectedItem ? selectedItem.Content.ToString() : "Nie wybrano";
            MessageBox.Show($"Dane pracownika:\nImię: {imie_txt.Text}\nNazwisko: {nazwisko_txt.Text}\nStanowisko: {stanowisko}", "Zatwierdzenie", MessageBoxButton.OK, MessageBoxImage.Information);
        }
    }
}
