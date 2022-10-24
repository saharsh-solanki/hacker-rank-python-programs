# hacker-rank-python-programs
# Search With Starting of the Question ( some question does not  have heading and a unique name search themm by the start) 



### Given the names and grades for each student in a class of  students, store them in a nested list and print the name(s) of any student(s) having the second lowest grade.
```
if __name__ == '__main__':
    records = []
    for _ in range(int(input())):
        name = input()
        score = float(input())
        records.append([name,score])
    records.sort(key=lambda item: item[1])
    sorted_list_in_reverse = [*records]
    ans_marks = 0
    ans_names = []
    start = 1
    min_main = sorted_list_in_reverse[0][1]
    for index,item in enumerate(sorted_list_in_reverse[1:len(sorted_list_in_reverse)]):
        if item[1] == min_main:
            start = start+1
        else:
            break
    for ans in sorted_list_in_reverse[start:len(sorted_list_in_reverse)]:
        if ans_marks == 0:
            ans_marks = ans[1]
            ans_names.append(ans[0])
        else:
            if  ans_marks == ans[1]:
                ans_names.append(ans[0])
            else:
                break
    ans_names.sort(key=lambda item: item[0])
    print("\n".join(i for i in ans_names))
    

```
