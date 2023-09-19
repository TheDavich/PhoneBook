# 📞 Phone Book App

## 📖 Overview

The Phone Book App is a contact management application that allows users to add, delete, and view their contacts. It follows modern Android app development practices, including the MVVM architecture, Dependency Injection (DI), and Room Database integration.

## 🧱 MVVM Architecture

The app follows the Model-View-ViewModel (MVVM) architecture:

### `ContactDao`

```kotlin
@Dao
interface ContactDao {
    // DAO methods...
}
```
The ContactDao interface defines the data access methods for interacting with the Room Database.

### `🗃️ ContactDatabase` 

```kotlin
@Database(
    entities = [Contact::class],
    version = 1
)
abstract class ContactDatabase: RoomDatabase() {
    abstract val dao: ContactDao
}
```
The ContactDatabase class represents the Room Database instance and provides access to the ContactDao.

### `ContactViewModel`

```kotlin
@OptIn(ExperimentalCoroutinesApi::class)
class ContactViewModel(private val dao: ContactDao): ViewModel() {
    // ViewModel code...
}
```
The ContactViewModel class manages UI data, communicates with the Room Database, and handles user interactions.

### `UI Components`

The user interface is built using Jetpack Compose and includes components like ContactScreen, AddContactDialog, ContactList, and more.

### `💉 Dependency Injection (DI)`
The app uses Dependency Injection (DI) for managing dependencies:

```kotlin
class MainActivity : ComponentActivity() {
    // Dependency setup code...
}
```
The MainActivity class sets up the Room Database and initializes the ContactViewModel with the ContactDao.

### `Room Database`
The app uses Room Database for storing and managing contact data.

### Data Classes
The project includes data classes like Contact to represent contact information.

## 🚀 Getting Started

To run the app locally, follow these steps:

1. Clone this repository.
2. Open the project in Android Studio.
3. Build and run the app on an Android emulator or device.

## 📷 Screenshots
