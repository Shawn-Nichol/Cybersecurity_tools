File entropy is very indicative of the suspiciousness of a file and is a prominent characteristic that these tools look for within a portable executable (PE). 

File entropy is a rating that scores how random the data  within a PE file is. A scale of 0 to 8.0 means less randomness of the data in the file, whereas a score towards 8 indicates this data is more random.

Malware authors use techniques such as encryption or packing to obfuscate their code and to attempt to bypass anti-virus. Because of this, these files will have high entropy. If an analyst had 1,000 files, they could rank the files by their entropy scoring; of course, the files with the higher entropy should be analyzed first. 

Packers use an executable as a source and output it to another executable. This executable will have had some  modifications made depending on the packer. Legitimate software developers use packing to reduce the size of their applications and to ultimately protect their work from being stolen. 

Entry point, When launched, this entry point is simply the location of the first pieces of code to be executed within the file as illustrated below. When an executable is packed, it must unpack itself before any code can execute. Because of this, packers change the entry point from the original location to what's called the unpacking stub. 

The unpacking stub will begin to unpack the executable into its original state. Once the program is fully unpacked, the entry point will now relocate back to its normal place to begin executing code. 

Question: What is the highest file entropy a file can have?
Answer: 8

Question: What is the lowest file entropy a file can have?
Answer: 0

Question: Name a common packer that can be used for application.
Answer: UPX
