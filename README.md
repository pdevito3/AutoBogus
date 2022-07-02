> **Note**
> This is a fork of [AutoBogus](https://github.com/nickdodd79/AutoBogus) by @nickdodd79 to introduce some critical missing features around .NET 6. This was created due to inactivity by Nick, but I'm hoping he comes back to continue supporting the library at some point. It is listed as `AutobogusLifesupport` on nuget. See below for the modified options

## .NET 6 support
This library has been updated to include .NET 6, an updated version of `Bogus` and auto fakers for DateOnly and TimeOnly structs introduced in .NET 6.

## Global WithDateTimeKind configuration
Gloablly configure your date time using one of the `DateTimeKind` types.

```c#
// Configure globally
AutoFaker.Configure(builder =>
{
  builder
    .WithLocale()         	// Configures the locale to use
    .WithDateTimeKind()     // Configures the DateTimeKind to use when generating date and time values. Defaults to `DateTimeKind.Local`.
    .WithRepeatCount()    	// Configures the number of items in a collection
    .WithDataTableRowCount()	// Configures the number of data table rows to generate
    .WithRecursiveDepth() 	// Configures how deep nested types should recurse
    .WithTreeDepth()		// Configures the tree depth of an object graph
    .WithBinder()         	// Configures the binder to use
    .WithFakerHub()       	// Configures a Bogus.Faker instance to be used - instead of a default instance
    .WithSkip()           	// Configures members to be skipped for a type
    .WithOverride();      	// Configures the generator overrides to use - can be called multiple times
});
