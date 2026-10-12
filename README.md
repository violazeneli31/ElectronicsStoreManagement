# 🛒 Marvis Electronics: Store Management System

A desktop application for running an electronics store, built in **Java** with a **JavaFX** interface. Employees log in and get a different dashboard depending on their role, **Cashier**, **Manager** or **Administrator**, each with its own features and permissions.

## Features

**🔐 Login:** Each employee signs in with their own username and password and is taken to the dashboard for their role.

**💵 Cashier**
- Create bills by adding products from a searchable product grid, with a live receipt and total
- Handle cash payment and change, with checks for missing or insufficient cash
- Register customers for a **client card** (unique client code and loyalty points that unlock 10–30% discounts)
- View today's bills and a chart of the total of all bills
- Every bill is saved as a receipt file with a unique ID

**📊 Manager**
- View each cashier's performance (bills, items sold and revenue) for one day or a date range
- Manage the inventory: add items, change prices, create categories, with **low-stock alerts**
- Store statistics: revenue vs. purchase cost, daily, monthly or yearly

**🛠️ Administrator**
- Add, edit and remove employees, change their passwords, and set **permissions** (e.g. whether a cashier can view today's bills)
- View the store's total cost and total income
- Manage suppliers

**All users:** a profile page and a change-password option (requires the current password).

**Other details**
- **Search bars** on every list (products, cashiers, employees, suppliers, inventory)
- **Input validation** with clear alert messages, e.g. empty bills, wrong client details, mismatched passwords or not enough cash paid
- **Permission checks:** if an employee's permission is removed, the action is blocked with an alert
- **Unique IDs** (UUIDs) for employees, suppliers, bills and client cards
- **Data is saved between runs:** changes to employees, inventory and bills stay after you close the app

## How it's built

- **Java 17+** and **JavaFX 21** for the user interface; **Maven** downloads JavaFX automatically for your system (Mac, Windows or Linux)
- **MVC structure:** `model` (the business classes), `view` (JavaFX screens), `controller` (connects them)
- **Object-oriented design:** `Cashier`, `Manager` and `Administrator` extend an abstract `Employee` class, with role-based permissions
- **Data storage:** employees and inventory are saved with Java serialization in `.dat` files, and bills are saved as text receipts

## Project structure

- **`src/`**: the source code (`main`, `model`, `view`, `controller`, `dao`), images, data files and saved bills
- **`documentation/`**: the project presentation, the UML class diagram (StarUML `.mdj`) and screenshots of the app
- **`pom.xml`**, **`mvnw`**: the Maven build setup

## How to run

You need **Java 17 or newer** (check with `java -version`). Download it from [Adoptium](https://adoptium.net) if you don't have it.

**Option 1: IntelliJ IDEA (easiest)**
1. **File → Open** and choose the project folder. If asked, choose **Trust Project** and open it as a **Maven** project.
2. Wait for it to finish loading. It downloads JavaFX the first time.
3. Open `src/main/Launcher.java` and click the green ▶ **Run** button.

**Option 2: Terminal**

```bash
./mvnw javafx:run          # Mac / Linux
mvnw.cmd javafx:run        # Windows
```

The first run downloads Maven and JavaFX automatically, so it needs an internet connection.

> Run the app from the **project folder** (IntelliJ does this by default), because the data files are loaded from `src/dao/`.
> A warning like `Unsupported JavaFX configuration` may appear in the console. It's harmless and the app works normally.

## Demo accounts

| Role          | Username  | Password      |
|---------------|-----------|---------------|
| Administrator | `sidrit`  | `sidrit2025`  |
| Manager       | `viola`   | `viola2025`   |
| Manager       | `arsildo` | `arsildo2025` |
| Cashier       | `megi`    | `megi2025`    |
| Cashier       | `argi`    | `argi2025`    |
| Cashier       | `marsi`   | `marsi2025`   |

## Authors

Sidrit Rrustemi, Viola Zeneli, Megi Almadhi and Arsildo Veliu
