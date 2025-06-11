# 📘 Dokumentacija za pokretanje projekta (.NET Core REST API)

## ✅ Neophodni alati i paketi za pokretanje aplikacije

### 1. Instalacija .NET SDK 9

- Neophodan za razvoj i pokretanje backenda
- Preuzeti .NET SDK 9 sa [zvaničnog sajta](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)
- Instalaciju pratiti prema uputstvu za vaš operativni sistem

---

### 2. Instalacija Visual Studio 2022/2023

- Preuzeti sa [zvanične stranice](https://visualstudio.microsoft.com/)
- Prilikom instalacije izabrati sledeće komponente:
  - ✅ ASP.NET and web development
  - ✅ .NET 8 SDK (ako nije već instaliran)
  - ✅ Data storage and processing (za MySQL podršku)
- Preporučene ekstenzije:
  - ✅ NuGet Package Manager (dolazi preinstaliran)

---

### 3. Instalacija NuGet paketa za backend (.NET)

Ukoliko paketi nisu već uključeni u projektu, instalirati sledeće preko Visual Studio-a:

- Otvoriti **Solution Explorer**
- Desni klik na projekat → **Manage NuGet Packages**
- Instalirati sledeće pakete:

- `Microsoft.AspNetCore.Authentication.JwtBearer`
- `Microsoft.EntityFrameworkCore.Design`
- `Microsoft.EntityFrameworkCore.Tools`
- `Pomelo.EntityFrameworkCore.MySql`

---

## ▶️ Pokretanje projekta

### 1. Konfiguracija baze (MySQL)

- Preuzeti i instalirati **MySQL Server** sa [zvanične stranice](https://dev.mysql.com/downloads/mysql/)
- Kreirati bazu podataka npr. `MyApiDb` putem MySQL Workbench-a ili komandne linije
- Ažurirati `appsettings.json`:

```json
"ConnectionStrings": {
  "DefaultConnection": "server=localhost;port=3306;database=MyApiDb;user=root;password=lozinka"
}
```

---

### 2. Kreiranje baze pomoću migracija

- Otvoriti Visual Studio
- Izabrati meni: **Tools → NuGet Package Manager → Package Manager Console**
- U konzoli pokrenuti sledeće komande:

```powershell
Add-Migration ImeMigracije
Update-Database
```

> Ovo će kreirati strukturu baze u MySQL-u koristeći Entity Framework Core

---

### 3. Pokretanje aplikacije

- Otvoriti rešenje u Visual Studio-u
- Uveriti se da je startup projekat pravilno podešen
- Kliknuti **Start (IIS Express)** ili **Run Without Debugging (Ctrl+F5)**

- Nakon pokretanja, API dokumentacija će biti dostupna putem **Scalar UI** interfejsa

  > Scalar je moderan OpenAPI UI za pregled i testiranje REST API-ja, kao zamena za Swagger.

---

## ℹ️ Napomene

- Scalar omogućava testiranje API-ja direktno kroz pregled interfejsa
- Za dodatne testove REST API-ja možete koristiti alate kao što su **Postman** ili **curl**
