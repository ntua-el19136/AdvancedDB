# Εργασία: Προχωρημένα Θέματα Βάσεων Δεδομένων 2024-25

Αυτό το αποθετήριο περιέχει την υλοποίηση της εξαμηνιαίας εργασίας για το μάθημα **Προχωρημένα Θέματα Βάσεων Δεδομένων** (ΣΗΜΜΥ, ΕΜΠ, Ακαδημαϊκό έτος 2024-25). Η εργασία περιλαμβάνει ανάλυση μεγάλων συνόλων δεδομένων, υλοποίηση ερωτημάτων με το Apache Spark και την αξιολόγηση διαφορετικών στρατηγικών εκτέλεσης.

---

## **Συγγραφείς**

- **Στέφανος Θέος (ΑΜ: 03119219)**
- **Αθανάσιος Μπιτσάνης (ΑΜ: 03119136)**

---

## **Περιγραφή Έργου**

Η εργασία βασίζεται σε δεδομένα εγκλημάτων του Los Angeles, αποθηκευμένα σε S3, καθώς και σε επιπρόσθετα σύνολα δεδομένων όπως:
- Δημογραφικά στοιχεία 
- Τοποθεσίες αστυνομικών τμημάτων
- Εισοδήματα νοικοκυριών 
- Κωδικοποίηση φυλετικών και εθνικών χαρακτηριστικών 

Στόχος είναι η υλοποίηση πολύπλοκων ερωτημάτων χρησιμοποιώντας το **Apache Spark** και τη βιβλιοθήκη **Apache Sedona** για χωρικές αναλύσεις.

---

## **Δεδομένα**

Τα δεδομένα της εργασίας βρίσκονται στο S3 bucket:  
`s3://initial-notebook-data-bucket-dblab-905418150721/`

### **Βασικά Σύνολα Δεδομένων**
- **Crime_Data_from_2010_to_2019_20241101.csv:** Καταγραφές εγκλημάτων στο Los Angeles.
- **Crime_Data_from_2020_to_Present_20241101.csv:** Καταγραφές εγκλημάτων μετά το 2020.
- **LA_Police_Stations.csv:** Τοποθεσίες αστυνομικών τμημάτων.
- **LA_income_2015.csv:** Μέσο εισόδημα ανά ταχυδρομικό κώδικα.
- **2010_Census_Blocks.geojson:** Απογραφικά στοιχεία.
- **RE_codes.csv:** Φυλετικά και εθνικά χαρακτηριστικά.


---

## **Απαιτήσεις**

Για την υλοποίηση και εκτέλεση του έργου απαιτούνται:
- **Apache Spark** (>=3.5.0)
- **Apache Sedona** (1.6.1)
- **Python** (>=3.8)
- **Boto3** για τη διαχείριση του AWS S3.

---

## **Ερωτήματα**

### Query 1: Ηλικιακές Ομάδες Θυμάτων
Υλοποίηση ερωτήματος που ταξινομεί, σε φθίνουσα σειρά, τις ηλικιακές ομάδες θυμάτων που εμπλέκονται σε περιστατικά "βαριάς σωματικής βλάβης".

### Query 2: Κατάταξη Αστυνομικών Τμημάτων
Εύρεση των 3 κορυφαίων αστυνομικών τμημάτων ανά έτος με βάση το ποσοστό κλεισμένων υποθέσεων. Περιλαμβάνει:
- Σύγκριση DataFrame και SQL APIs
- Μετατροπή δεδομένων από CSV σε Parquet και μέτρηση χρόνων εκτέλεσης.

### Query 3: Εισόδημα και Εγκληματικότητα
Υπολογισμός μέσου εισοδήματος και αναλογίας εγκλημάτων ανά άτομο για περιοχές του Los Angeles.

### Query 4: Φυλετικό Προφίλ Θυμάτων
Ανάλυση φυλετικών δεδομένων για περιοχές με το υψηλότερο και χαμηλότερο εισόδημα.

### Query 5: Εγκλήματα πλησιέστερα σε Αστυνομικά Τμήματα
Υπολογισμός εγκλημάτων και μέσης απόστασης περιστατικών από τα πλησιέστερα αστυνομικά τμήματα.

---

## **Περιεχόμενα Αποθετηρίου**

- **Query1.ipynb**: Κώδικας για την υλοποίηση του Query 1
- **Query2a.ipynb**: Κώδικας για την υλοποίηση του Query 2α
- **Query2b.ipynb**: Κώδικας για την υλοποίηση του Query 2β
- **Query3.ipynb**: Κώδικας για την υλοποίηση του Query 3
- **Query4.ipynb**: Κώδικας για την υλοποίηση του Query 4
- **Query5.ipynb**: Κώδικας για την υλοποίηση του Query 5
- **README.md**: Αρχείο ReadMe για την περιγραφή της εργασίας.

---

## **Τρόπος Εκτέλεσης**

### Βήματα:
- Σύνδεση στην πλατφόρμα Amazon Web Services (AWS)
- Πλοήγηση στο Amazon SageMaker AI 
- Επιλογή Notebooks από το sidebar στο αριστερό μέρος της οθόνης
- Αναζήτηση του "group29-sagemaker-notebook" και πλοήγηση σε αυτό (https://eu-central-1.console.aws.amazon.com/sagemaker/home?region=eu-central-1#/notebook-instances/group29-sagemaker-notebook)
- Επιλογή "Open Jupyter" για προβολή των υλοποιημένων queries στα αρχεία .ipynb
- Επιλογή του προς εξέταση αρχείου και επιλογή "Run" για την εκτέλεση του κώδικά του και προβολή των αποτελεσμάτων

### Σημειώσεις για την εκτέλεση:

- Για την υλοποίηση των queries, χρησιμοποιούνται τα προαναφερθέντα σύνολα δεδομένων, τα οποία βρίσκονται στον χώρο αποθήκευσης S3, στο general purpose bucket "initial-notebook-data-bucket-dblab-905418150721".
(https://eu-central-1.console.aws.amazon.com/s3/buckets/initial-notebook-data-bucket-dblab-905418150721?region=eu-central-1&bucketType=general&tab=objects)

- Το αρχείο .parquet που παράγεται από τον κώδικα του Query 2β, είναι αποθηκευμένο στον φάκελο "group29" του general purpose bucket "groups-bucket-dblab-905418150721", του χώρου αποθήκευσης S3.
(https://eu-central-1.console.aws.amazon.com/s3/buckets/groups-bucket-dblab-905418150721?region=eu-central-1&bucketType=general&prefix=group29/&showversions=false)

---

## **Σημειώσεις**

- Οι χρόνοι εκτέλεσης εξαρτώνται από τις ρυθμίσεις των Spark Executors και τη διαθεσιμότητα πόρων.
- Για την εκτέλεση queries με geospatial analytics, απαιτείται η χρήση της βιβλιοθήκης Apache Sedona.

---

Για οποιεσδήποτε ερωτήσεις ή διευκρινίσεις, παρακαλώ επικοινωνήστε με την ομάδα.
