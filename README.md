# Automated-Code-Converter-
Reads C# code that has not been formatted, and creates a file with the code formated with proper indents and line counts.


using System;
using System.IO;
static class Cool
{
	static void Main()
	{
		string fileName = "final.txt";
		StreamReader sr = new StreamReader (fileName);
		StreamWriter sw = new StreamWriter ("NoahK.cs") ;
		while(!sr.EndOfStream)
		{
			string line = sr.ReadLine(); 
			string [] array = line.Split(" ".ToCharArray());
			
				string x = "1";
				int lineNumber = 2;
				int tabCounter = 0;
				for(int i = 0; i < array.Length; i++)
				{
					if(array[i] == "{")
					{
						tabCounter++;	
					}
					if(array[i] == "}")
					{
						tabCounter--;
					}
				
				
					if(array[i] != lineNumber.ToString() )
					{
						if(array[i] != x)
						{
							sw.Write(array[i] + " ");
						}
						else
						{
							x = "hawian pizza";
						}
					}
					else
					{
						sw.Write(Environment.NewLine);
						int j = 0;
						if(array[i+1] == "}")j=1; 
						for(; j < tabCounter; j++)
						{
							sw.Write("\t");
						}
						lineNumber++;
					}
				
			
				}
				
			
		
		}
		sr.Close();
		sw.Close();

	}
}
		
