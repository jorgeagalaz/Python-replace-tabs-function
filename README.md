# Python-replace-tabs-function
This function replace tabs from spaces, in python


def tab_to_space (line, tab_lenght = 8):
    """this function change all the tabs ('\\t') for spaces in a string, 
        the lenght of the tabs is 8 by default"""

    while '\t' in line:
        first_tab_init_pos = line.find('\t')
        first_tab_end_pos = (((first_tab_init_pos // tab_lenght)+1) * tab_lenght)
        diff = first_tab_end_pos - first_tab_init_pos
        if diff == 0:
            spaces_string = ' ' * tab_lenght
        else:
            spaces_string = ' ' * diff
        line = line.replace('\t', spaces_string, 1)
    return line


inputfile = open('inputfile.txt', 'r')
outputfile = open('outputfile.txt', 'w')
for line in inputfile:
    line = tab_to_space(line)
    outputfile.write(line)
inputfile.close()
outputfile.close()
