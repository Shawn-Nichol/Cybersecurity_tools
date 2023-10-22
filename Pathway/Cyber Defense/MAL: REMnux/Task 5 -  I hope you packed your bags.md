FIle entropy is vvery indicative of the suspiciousness of a file and is a prominent characteristic that these tools look for within a portable executable (PE). 

File entropy is a rating that scores how random the data  within a PE file is. With a scale of 0 to 8.0 meaning the less randomness of the data in the file, where a scorign towrads 8 indicates this data is more random.

Malware authors use techniques such as encryption or packing to obfuscate their code and to attempt to bypass anti-virus. Becuase of this these files will have high entropy. If an analyst had 1,000 files, they could rank thefiles by their entropy scoring, of course, the files with the higher entropy should be analysed first. 

Packer's use an executable as a rouce and output it to another executable. This executable will have had some  modificatios made depending on the packer. Legitimate software developers use packing to reduce the size of their applications and to ultimaely protect their work from being stolen. 

Entry point, W:hen launched, this entry point is simply the location of the first pieces of code to be executed within the file as illustraded below. When an executable is packed, it must unpack itself before any code can execute. Becuase of this, packers change theentry pointfrom the oringal location to what's calle dthe unpacking stub. 

Unpacking stub will begin to unpack the exeutable into its oringal state. Once the progam is fully unpacked, the entry point will now relocate back to its normal place to begin executing code. 

Question: What is the highest file ntropy a file can have?
Answer: 8

Question: What is the lowest file entropy a file can have?
Answer: 0

Question: Name a common packer that can be used for application?
Answer: UPX
