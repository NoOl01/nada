# nada
# Кодировщик
```
class PasswordEncoderDecoder
{
    static void Main()
    {
        Console.WriteLine("Введите пароль для кодирования:");
        string password = Console.ReadLine();

        string encodedPassword = EncodePassword(password);
        Console.WriteLine($"Закодированный пароль: {encodedPassword}");

        string decodedPassword = DecodePassword(encodedPassword);
        Console.WriteLine($"Раскодированный пароль: {decodedPassword}");
    }

    static string EncodePassword(string password)
    {
        byte[] data = System.Text.Encoding.Unicode.GetBytes(password);
        string encodedPassword = Convert.ToBase64String(data);
        return encodedPassword;
    }

    static string DecodePassword(string encodedPassword)
    {
        byte[] data = Convert.FromBase64String(encodedPassword);
        string decodedPassword = System.Text.Encoding.Unicode.GetString(data);
        return decodedPassword;
    }
}
```

#отправка сообщений через WPF
```
var cl = db.Clients.ToList();
var mail = db.Mails.ToList();
foreach(Clients c in cl)
{
    foreach(Mail m in mail)
    {
        if(c.ClientPhone == m.ClientPhone)
        {
            Message result;
            DoSomethingAsync($"{c.ClientId}", $"Ваш заказ прибыл: {m.Number}\n" +
                $"Заберите его до {m.Date}");
            async Task DoSomethingAsync(string destID, string text)
            {
                var bot = new Telegram.Bot.TelegramBotClient("7014504643:AAGxZu_tHAiplOsO_7uVqVe_LXjZwNpy84I");
                await bot.SendTextMessageAsync(destID, text);
            }
        }
    }
}
```
#Проверка что это номер телефона
```
string strPattern=@"(\+7|8|\b)[\(\s-]*(\d)[\s-]*(\d)[\s-]*(\d)[)\s-]*(\d)[\s-]*(\d)[\s-]*(\d)[\s-]*(\d)[\s-]*(\d)[\s-]*(\d)[\s-]*(\d)";
if (Regex.IsMatch(message.Text, strPattern, RegexOptions.IgnoreCase))
```
#Токен для бота
```
7080102638:AAEctYLr_mdAuHjl-037eGg_7aVW09LGSWw
```
