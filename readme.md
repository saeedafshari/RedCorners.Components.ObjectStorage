RedCorners.Components.ObjectStorage enables easy cross-platform storage of settings as JSON in C#.

NuGet: [https://www.nuget.org/packages/RedCorners.Components.ObjectStorage](https://www.nuget.org/packages/RedCorners.Components.ObjectStorage)
GitHub: [https://github.com/saeedafshari/RedCorners.Components.ObjectStorage](https://github.com/saeedafshari/RedCorners.Components.ObjectStorage)

## Dependencies

RedCorners depends on `Newtonsoft.Json` for JSON serialization and deserialization.

## Example

```c#
using System;
using System.Collections.Generic;
using RedCorners.Components;

class Program
{
	public class Settings
	{
		public int Count { get; set; }
	}

	static void Main(string[] args)
	{
		var settings = new ObjectStorage<Settings>();
		
		// First time it's 0, and every time you run the app it gets increased by 1.
		Console.WriteLine($"Default Count: {settings.Data.Count}");

		settings.Data.Count++;
		settings.Save();

		Console.WriteLine($"New Count: {settings.Data.Count}");
	}
}
```