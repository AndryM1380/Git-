# Git-
**SQL-инъекциями** называют атаки, позволяющие злоумышленнику производить различные несанкционированные действия над базой данных. Они могут затрагивать как сами данные, так и структуру базы. Для этого в качестве входных данных передаются специальные строки, содержащие вредоносные команды. Приложение, уязвимое к SQL-инъекциям, производит вставку этих строк в шаблон запроса без проведения необходимых проверок. В результате формируется запрос, выполняющий действия, определённые злоумышленником. При этом запрос будет являться корректным с точки зрения синтаксиса SQL.
*Пример уязвимости*

void ProcessRequest(HttpRequest request) 
{ 
  string name = request.Form["name"];

  string sql = $"SELECT * FROM Users WHERE name='{name}'";
  ExecuteReaderCommand(sql);

  .... 
}

void ExecuteReaderCommand(string sql) 
{
  using (var command = new SqlCommand(sql, _connection))
  { 
    using (var reader = command.ExecuteReader()) { .... } 
  } 
  .... 
}
Поиск потенциальных уязвимостей
void ProcessRequest(HttpRequest request) 
{ 
  string name = request.Form["name"];

  string sql = $"SELECT * FROM Users WHERE name='{name}'";
  ExecuteReaderCommand(sql);

  .... 
}

void ExecuteReaderCommand(string sql) 
{
  using (var command = new SqlCommand(sql, _connection))
  { 
    using (var reader = command.ExecuteReader()) { .... } 
  } 
  .... 
}
Борьба с SQL-инъекциями
String userName = Request.Form["name"];

using (var command = new SqlCommand()
{
  Connection = _connection,
  CommandText = "SELECT * FROM Users WHERE UserName = @userName",
  CommandType = System.Data.CommandType.Text
})
{
  var userNameParam = new SqlParameter("@userName", userName);
  command.Parameters.Add(userNameParam);
            
  using (var reader = command.ExecuteReader()) { .... }
}
https://ru.wikipedia.org/wiki/%D0%92%D0%BD%D0%B5%D0%B4%D1%80%D0%B5%D0%BD%D0%B8%D0%B5_SQL-%D0%BA%D0%BE%D0%B4%D0%B0
