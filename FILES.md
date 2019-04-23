# FILES:

#### create a file
	File file = new File("myFile.txt");
	file.createNewFile();


#### FileWriter
	new FileWriter(file).write("howdy\nfolks\n");	// creates a file and writes char by char
	fw.flush(); 					// flush before closing
	fw.close();					// close file when done


#### FileReader
	char[] in = new char[50]; 			// to store input
	new FileReader(file).read(in);			// reads file char by char and put into 'in'

cons of FileWriter:
	- \n manually written
cons of FileReader:
	- declare the array size before hand
	- reads data 1 char at a time, looking for the end of file each after each read()


#### BufferedWriter vs PrintWriter
1. Writing using BufferedWriter:
	.write()				//line1
	.newLine()				//line2
2. Writing using PrintWriter:
	.println()				//line1 (prints character[]/String and then prints a new line)
(NOTE: Therefore to write, PrintWriter is better than BufferedWriter)


#### PrintWriter: best for writing into a file
	File file = new File("fileWrite2.txt"); 	// create a File
	PrintWriter pw = new PrintWriter(file);
	pw.println("howdy folks");

#### BufferedReader: best for reading from a file
	File file = new File("fileWrite2.txt"); 	// create a File object AND open "fileWrite2.txt"
	FileReader fr = new FileReader(file); 		// create a FileReader to get data from 'file'
	BufferedReader br = new BufferedReader(fr); 	// create a BufferReader to get its data from a Reader
	String data = br.readLine();			// read some data
	while( (s = br.readLine()) != null)		// read the whole file line-by-line


#### create a file
	File file = new File("myFile.txt");		// if myFile already exists, file refers to that
	file.createNewFile();				// if myFile already exists, this line of code is not needed


#### create a directory
	File dir = new File("myDir");
	dir.mkdir();


#### create a file inside a directory
	File file = new File(dir, "myFile.txt");
	file.createNewFile();


#### delete
	file.delete();					// delete a file
	dir.delete();					// delete a directory (ONLY IF ITS EMPTY!)


#### rename a file
	File newFile = new File(dir, "myNewFile.txt");
	file.renameTo(newFile);


#### rename a directory
	File newDir = new File("myNewDir");
	newDir.renameTo(newDir);


#### list all files and directories inside a directory
	File dir = new File("myDir");
	String[] filesAndDirectories = new String[100];
	filesAndDirectories = dir.list();		// create a String array of files and directories present inside dir
	for(String fn : files) 				// iterate through it
	  System.out.println("found " + fn);


# CONSOLE:

#### important methods:
 - System.console(): 	returns Console object
 - readLine(): 		returns String	(takes String s input -> %s)
 - readPassword(): 	returns char[ ] (but takes String s input -> %s)
 - format(): 		prints 
