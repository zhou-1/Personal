# Intersection      
get the same elements from two group.   
retainAll(), if we have two <b> sets/lists </b>, newCourses and oldCourses. When we use oldCourses.retainAll(newCoures), if there are same elements between two sets, oldCourses includes same elements; otherwise, oldCourses become emepty.    
i.e. oldCourses = [1, 3, 5], newCourses = [1, 2, 3], use oldCourses.retainAll(newCoures), Intersection result will be [1, 3]   


# Difference   
get the different element from two element.   
removeAll(), if we have two <b> sets/lists </b>, newCourses and oldCourses. When we use oldCourses.removeAll(newCoures), if there are different elements between two sets, oldCourses includes the special element from its original set/list; otherwise, oldCourses become emepty.    
i.e. oldCourses = [1, 3, 5], newCourses = [1, 2, 3], use oldCourses.removeAll(newCoures), difference result will be [2]   

# Combine   
Different for set and list.   
set: combine elements and get rid of duplicates.   
list: combine all elements and not get rid of duplicates.   
    
    Set<Integer> result = new HashSet<Integer>();
    result.addAll(set1);
    result.addAll(set2);

set 1 is [1, 3, 5], set2 is [1, 2, 3], result will be [1, 2, 3, 5].    

    List<Integer> list = new ArrayList<Integer>();
    list.addAll(list1);
    list.addAll(list2);

list1 is [1, 3, 5], list2 is [1, 2, 3], result will be [1, 3, 5, 1, 2, 3].    

