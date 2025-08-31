# EasyApiCaller

**EasyApiCaller** is a lightweight and easy-to-use C# library for making HTTP API calls. It simplifies GET, POST, PUT, and DELETE requests using `HttpClient` and automatically serializes/deserializes JSON objects.

---

## Features

- Perform **GET**, **POST**, **PUT**, and **DELETE** requests easily.
- Automatic JSON serialization/deserialization using `System.Text.Json`.
- Generic methods to directly return strongly typed objects.
- Lightweight, dependency-free wrapper around `HttpClient`.

---

## Installation

You can install the NuGet package via:

```bash
dotnet add package EasyApiCaller

```
## Usage
GET Request
using EasyApiCaller;

var result = await EasyApiCall.Get<MyResponseType>("https://api.example.com/data");

## POST Request
using EasyApiCaller;

var payload = new { Name = "John", Age = 30 };
var result = await EasyApiCall.Post<MyResponseType>("https://api.example.com/users", payload);

## PUT Request
using EasyApiCaller;

var updatePayload = new { Name = "John Doe" };
var result = await EasyApiCall.Put<MyResponseType>("https://api.example.com/users/1", updatePayload);


## DELETE Request
using EasyApiCaller;

var result = await EasyApiCall.Delete<MyResponseType>("https://api.example.com/users/1");


## Notes

The methods throw exceptions if the HTTP request fails (response.EnsureSuccessStatusCode()).

Ensure that your response types match the expected JSON structure.

For custom headers or authentication, you can configure the _client directly:

## EasyApiCall.Client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_TOKEN");


# License

MIT License.

✅ This is **all-in-one**, ready to include in your NuGet package.  

If you want, I can also **add a “full example project” section** inside the same README so users can copy-paste and test immediately. Do you want me to do that?
