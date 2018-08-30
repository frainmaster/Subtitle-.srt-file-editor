print('input path of the subtitle file you want to edit:')
path = input() + '/'
path1 = path
print('input the subtitle file name:')
path += input()
name = list(path)
path = ''
for i in range(0, len(name)):
    if name[i] == '\\':
        path += '/'
    else:
        path += name[i]
print(path)

print('name of new file?')
name = input()

print('by how many seconds you want to increase the timer?\n'
      'Write in seconds, up to 3 decimal places.')
# this accepts seconds input in float, change into milliseconds (*1000) and convert into integer, simultaneously.
add = int(float(input())*1000)
print(str(add) + 'ms')

with open(path, 'r') as file:
    with open(path1 + name + '.srt', 'w') as file2:
        for lines in file:
            time = []
            ms = s = m = h = ms2 = s2 = m2 = h2 = ''
            if (len(lines) == 30) & (lines[13:16] == '-->'):
                print(lines[0:len(lines)-1])
                # convert all lines with time into a uniform count: seconds
                sec = int(lines[0])*36000000 + int(lines[1])*3600000 + \
                      int(lines[3])*600000 + int(lines[4])*60000 + int(lines[6])*10000 + \
                      int(lines[7])*1000 + int(lines[9])*100 + int(lines[10])*10 + int(lines[11])*1
                sec2 = int(lines[17])*36000000 + int(lines[18])*3600000 + \
                       int(lines[20])*600000 + int(lines[21])*60000 + int(lines[23])*10000 + \
                       int(lines[24])*1000 + int(lines[26])*100 + int(lines[27])*10 + int(lines[28])*1
                sec += add
                sec2 += add
                # sec
                for i in range(3-len(str(sec % 1000))):
                    ms += '0'
                time.append(ms + str(int(sec % 1000)))
                sec = int(sec/1000)
                for i in range(0, 2-len(str(sec % 60))):
                    s += '0'
                time.append(s + str(int(sec % 60)))
                sec = int(sec/60)
                for i in range(2-len(str(sec % 60))):
                    m += '0'
                time.append(m + str(int(sec % 60)))
                sec = int(sec/60)
                for i in range(2-len(str(sec % 60))):
                    h += '0'
                time.append(h + str(int(sec % 60)))

                # sec2
                for i in range(3-len(str(sec2 % 1000))):
                    ms2 += '0'
                time.append(ms2 + str(int(sec2 % 1000)))
                sec2 = int(sec2/1000)
                for i in range(0, 2-len(str(sec2 % 60))):
                    s2 += '0'
                time.append(s2 + str(int(sec2 % 60)))
                sec2 = int(sec2/60)
                for i in range(2-len(str(sec2 % 60))):
                    m2 += '0'
                time.append(m2 + str(int(sec2 % 60)))
                sec2 = int(sec2/60)
                for i in range(2-len(str(sec2 % 60))):
                    h2 += '0'
                time.append(h2 + str(int(sec2 % 60)))
                print('{0}:{1}:{2},{3} --> {4}:{5}:{6},{7}\n'
                      .format(time[3], time[2], time[1], time[0], time[7], time[6], time[5], time[4]))
                file2.write('{0}:{1}:{2},{3} --> {4}:{5}:{6},{7}\n'
                      .format(time[3], time[2], time[1], time[0], time[7], time[6], time[5], time[4]))
            else:
                file2.write(lines)