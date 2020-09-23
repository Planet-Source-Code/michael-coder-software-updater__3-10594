<div align="center">

## Software Updater


</div>

### Description

With this code you can distribute software over the internet and if you ever need to update your programme you don't need to make everyone download the entire programme again or let some users use the outdated software but can simple update the version file to 2 for example and have everyone download the new update.

You need to make sure that the direct download link to your programme is always the same or else you would need to update the link for your programme every time there would be an update.
 
### More Info
 
How the code works:

Downloads a file from the internet e.g. a text file with a version number e.g. 1

opens the file and saves the content of the downloaded file and checks if its the same value of the current programme. If it is you can carry on using the programme however if not you are presented with a menu where you can chose to visit the download page or directly download the files or exit.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[michael coder](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/michael-coder.md)
**Level**          |Intermediate
**User Rating**    |4.7 (14 globes from 3 users)
**Compatibility**  |C\+\+ \(general\), Microsoft Visual C\+\+
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/michael-coder-software-updater__3-10594/archive/master.zip)

### API Declarations

```
#include &lt;windows.h&gt;
#include &lt;iostream&gt;
using namespace std;
//project must be linked to: urlmon.lib
```


### Source Code

```
#include <windows.h>
#include <iostream>
using namespace std;
bool updated=false;
void menu (){
	int option;
	cout<<"Update Options\n";
	cout<<"1) Visit download page\n";
	cout<<"2) Automatically download the latest file version\n";
	cout<<"3) Exit\n";
	cout<<">>";
	cin>>option;
	switch(option)
	{
  case 1:
		ShellExecute(NULL, "open", "Download page link" , NULL, NULL, SW_SHOWNORMAL);
  exit(1);
		break;
  case 2:
		URLDownloadToFile (NULL, "direct download link to your programme", "name of programme e.g. software.exe", 0, NULL);
		exit(1);
		case 3:
		exit(1);
	}
}
int main (){
	cout<<"Checking for newer versions...\n";
	URLDownloadToFile (NULL, "download link to a file e.g. Version.txt", "name of file", 0, NULL);
	FILE *ptr;
	int ch;
	ptr = fopen("The name your named it","r");
	cout<<"You are using version ";
	if(ptr != NULL){
		ch=fgetc(ptr);
		putchar(ch);
		fclose(ptr);
	}
	int ch1=ch-48;
	if (ch1==1){ /*change the value of 1 to the newest versions number*/
		cout<<"\nYou already have the newest version\n";
		updated=true;
	}
	else{
		cout<<"\nYour software is out-dated and needs updating...\n";
		menu ();
	}
	if (updated=true){
		cout<<"Now that this programme is updated you can use it\n";
		/*add any programmes code in here*/
	}
	system("PAUSE");
	return 1;
}
/*Good luck*/
```

