CustomComparator
================

This jar helps you be able to sort objects based on a string value inside the object (the string value being alphanumeric)

**Problems with Comparable and String.CASE_INSENSITIVE_ORDER**
- Alphanumeric strings are not sorted correctly

Given:
- Grade 1
- Grade 2
- Grade 13

The result set is:
- Grade 1
- Grade 13
- Grade 2

**How to use CustomComparator**
- Use Collections.sort method to sort the object list, and pass the CustomComparator Object that takes the Class being compared, the methodname used for sorting, and the Class type

**For example:**
```
public static List<Grades> getSortedList(List<Grades> gradeList, Class<?> classType, String methodName) {
		Collections.sort(gradeList, new CustomComparator<Grades>(classType, methodName));
		return gradeList;
}
```

Grades is the class that needs to be sorted, so we pass the list of Grades class, and the classType as Grades.class and the method name that needs to be used to sort the class

**Input**
- Grade 1
- Grade 13
- Grade 6
- Grade 4
- PRE-K
- K

**Output**
- Grade 1
- Grade 4
- Grade 6
- Grade 13
- K
- PRE-K
