"vsechny knihy od Orwella"
Books select: [:b | b author surname = 'Orwell']

"vsechny ratings od uzivatele john_doe"
Ratings select: [:r | r user username = 'john_doe']

"knihy s rating > 4"
Books select: [:b | b averageRating > 4]

"knihy s rating > 4 serazené sestupne podle ratingu"
(Books select: [:b | b averageRating > 4]) asSortedCollection: [:a :b | a averageRating > b averageRating]

"knihy serazené sestupne podle ratingu"
Books asSortedCollection: [:a :b | a averageRating > b averageRating]

"debut autora"
(Books asSortedCollection: [:a :b | a publicationYear < b publicationYear]) detect: [:b | b author fullName = 'Dick Francis']

"poslední autorovo dílo"
(Books asSortedCollection: [:a :b | a publicationYear > b publicationYear]) detect: [:b | b author fullName = 'Dick Francis']

"vsechny knihy od Dicka Francise"
Books select: [:b | b author fullName = 'Dick Francis']