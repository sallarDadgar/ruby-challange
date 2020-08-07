# Refactoring Challenge

During support we sometimes write some quickfix solutions, which we think will
not be needed apart from that one time task. Thus the code usually has no
tests, is not documented and just everything in one large file. Attached you
find an example for such an assumed one time task - modifier.rb.

Please do the following:

- give a short explanation of what the code actually does.
- refactor the code and ensure that the refactored code does the same
  as before.
- create a git repository containing the initial files and do regular
  and small commits to log your process.
- send me your git bundle containing your changes.

=====================================================================================================
1) in first step the latest method will be called which takes a string as an argument and finds every file in the specific directory that has this striing in its name and sorts these files based on a date that exists in their name and then returns the date of the last file...

2) then an object of the calss Modifier will be created. this class takes two arguments, saleamount_factor and cancellation_factor.

3) by the object created, the method modify will be called and two arguments will be given,output and input which are the result of calling the latest method( step one ).

3-1) the first action will be calling the sort method on input, where the file will be read as a CSV and its content and headers will be seperated and sent to another method called write as arguments. in the write method, all the data and the headers will be added to variable and sent back to the sort method which will be the result( output ) of the sort method as well.

3-2) last steps result will be sent to lazy-read as an argument,where every line of it will be read as a CSV.

3-3) the read data will be an argument for the combine method of class Combiner where in every cell of the csv data, instead of nil another data(-1, 0, 1) will be used and an array will be sent back to modify method and will be saved in a variable called combiner.

3-4) every element of combiner will be sent to a method named combine_hashes, where a hash will be created inwhich the key is the header for every column and the value is an array of all the data that belongs to that header. this hash will be saved in a variable named merged.

3-5) merged will be sent to combine_values method as an argument. in this method some keys that have been defined in the Modifier class will be used. first the values of the hash(merged) will be outof array form for certain keys that have been defined previously ana then convert some of them that are integers into string. for certain keys such as "number of commissions", the value will be changed by factoring in saleamount_factor and cancellation_factor and the hash willbe returned as the result of this method and will be saved as merger.

3-6) eventually the data in merger will be put in a csv file with the same name as the input file followed by an index that starts from zero and in each file thete will be upto 120,000 lines of data, and if there is more data the it will be saved into another csv file in the same directory with only index changed and increased by one, to differ between files.
=====================================================================================================
