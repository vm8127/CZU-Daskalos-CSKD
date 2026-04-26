# Custom Methods Reference

## Overview
This document provides a reference of custom methods defined in the Daskalos project, excluding getters and setters.

---

## Author

### `fullName`
Concatenates `name` and `surname` with a space separator.

```smalltalk
fullName
	^name , ' ' , surname
```

---

## Book

### `age`
Calculates the book's age by subtracting its `publicationYear` from the current year.

```smalltalk
age
	^Date today year - publicationYear
```

### `averageRating`
Computes the average rating for the book by:
1. Finding all `Rating` instances where the book matches this book
2. Collecting their `value` fields and calculating the average
3. Returns 0 if no ratings exist

```smalltalk
averageRating
	| ratings |
	ratings := Rating allInstances select: [:r | r book = self].
	ratings isEmpty ifTrue: [^0].
	^(ratings collect: [:r | r value]) avg asFloat
```

---

## Rating

### `isMasterpiece`
Returns true if the rating `value` is 4 or higher.

```smalltalk
isMasterpiece
	^value >= 4
```

### `value:` (Custom Setter)
Sets the rating value with constraints—bounds the value between 0 and 5.

```smalltalk
value: anObject 
	value := ((self checkValue: anObject forVariable: #value) max: 0) min: 5
```

---

## User

No custom methods defined. Only getters/setters and initialization.
