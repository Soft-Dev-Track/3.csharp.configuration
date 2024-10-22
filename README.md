# 3.Configuration

In this section, let's create a new project in **Visual Studio** Or with **Terminal & VSCode**.

- <a href="#Microsoft Visual Studio">Visual Studio Code</a>
- <a href="#terminal--vs-code">VScode & Terminal</a>

## Microsoft Visual Studio

### 1. Create a new project

<img src="assets/get_started.png" width=400/>

### 2. Select **Console App**

<img src="assets/new_project.png" width=1000/>

Select `Console App`

### 3. Configure your new project

<img src="assets/configure.png" width=500/>

- **Project name:** It is the ame of your project
- **Location:** Please, create a directory for this course
- **Solution name:** it is the name of the directory where all your projects will be placed

So, in this case it will be : `C:\Users\BeCode\OneDrive\Documents\Courses`

### 4. Additional info

<img src="assets/additional.png" width=500/>

Please, check `Do not use top-level statements`

### 5. You are now ready

<img src="assets/vs.png" width=500/>

## Terminal & Vs Code

```bash
# Generate the sln file
dotnet new sln -o courses
```

> .sln file: Visual Studio solution file, organizes projects, manages dependencies, stores configurations.

```bash
# Create a new Console App
cd courses
dotnet new console -o Fundamentals

// This command adds your project in the sln file (Solution)
dotnet sln ./courses.sln add ./Fundamentals/Fundamentals.csproj
```

Open your **Program.cs** from your Fundamentals.App and update this code by. If you don't understand what is written below, don't worry. We will cover OOP (Object-Oriented Programming) later.

```csharp
Console.Writeline("Hello World");
```

```csharp
namespace fundamentals.App
{
    public class Program
    {
        public static void Main(string[] args)
        {
            // Your code here
        }
    }
}
```

```csharp
# In your directory Fundamentals
dotnet run
```

## Unit Tests

For all of your exercises, unit tests will be provided. They will be written for you, so you don't need to worry about that. You will find them in each chapter where exercises are presented. Now, let's see how to implement unit tests in your C# projects

### Microsoft Visual Studio

### 1. Add a new project in your solution

<img src="assets/add_new_project.png" width=500/>

### 2. Choose Nunit

<img src="assets/choose_Nunit.png" width=500/>

### 3. Tie the projects

<img src="assets/project_reference.png" width=500/>

### 4. Update your code

```csharp

// Fundamentals folder

namespace Fundamentals
{
    public class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
        }

        public static string Hello()
        {
            return "Hello";
        }
    }
}

// TestFundamentals folder
namespace TestFundamentals
{
    public class Tests
    {
        [Test]
        public void TestHello()
        {
            Assert.That(Fundamentals.Program.Hello(), Is.EqualTo("Hello"));
        }
    }
}
```

- **Note:** To launch the tests, go to `Test > Run all tests`.

### VSCode

Go the the root of your project

```bash
cd ..
dotnet new nunit -o Testfundamentals

# Alway in your root directoryon)
dotnet sln ./courses.sln add ./TestFundamentals/Testfundamentals.csproj
```

## Last thing ...

we’ll need to tie this project to our application. First, we’ll add a reference to the application. In the console, in your fundamentals.Test folder, type in the following:

```bash
cd TestFundamentals
dotnet add reference ..\Fundamentals\Fundamentals.csproj
```
