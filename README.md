# cs-exam
#first I define the function that is going to do all the work for us 
def search_for_this(file,list):
    #line_num is used to decide the number of line the word is in
    line_num=0
    #we declare the list of words for the words found in the file to to appended in later
    list_of_words=[]
    #reading the file :)
    with open(file,'r') as read_file:
        for line in read_file :
            line_num+=1
            for words in list :
                if words in line:
                    #here we append the words found in the file to the list of words we declared earlier+ the line_num + the line itself
                    list_of_words.append((words,line_num,line.rstrip()))

    return list_of_words

the_lines = search_for_this('names.txt', ['Giovanni', 'Ernesto'])

for elem in the_lines:
    print('word= ',elem[0],'\n' , 'line number = ',elem[1] ,'\n' , 'line = ',elem[2])
    
