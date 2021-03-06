# Αντλίες Medtronic

**>>>> Το πρόγραμμα οδήγησης της αντλίας Medtronic δεν είναι ακόμα μέρος του master AndroidAPS. Θα είναι διαθέσιμο στην επόμενη κύρια έκδοση. <<<<**

* * *

Λειτουργεί μόνο με παλαιότερες αντλίες Medtronic (βλ. λεπτομέρειες παρακάτω). Δε λειτουργεί με την Medtronic 640G και 670G.

* * *

Ενώ το πρόγραμμα οδήγησης της Medtronic δοκιμάστηκε με καλή δοκιμαστική ομάδα, εξακολουθεί να θεωρείται λογισμικό beta, πράγμα που σημαίνει ότι έως ότου ένα μεγαλύτερο κοινό το δοκιμάσει για μεγαλύτερο χρονικό διάστημα, θα χρειαστεί να ενεργοποιήσετε τη λειτουργία Engineering, για να μπορείτε να δείτε τον οδηγό στο AndroidAPS.

* * *

## Απαιτήσεις υλικού και λογισμικού

- ** Τηλέφωνο: ** Ο οδηγός Medtronic θα πρέπει να λειτουργεί με οποιοδήποτε τηλέφωνο που υποστηρίζει BLE. ** ΣΗΜΑΝΤΙΚΟ: Ενώ το πρόγραμμα οδήγησης λειτουργεί σωστά σε όλα τα τηλέφωνα, δεν επιτρέπεται η ενεργοποίηση / απενεργοποίηση του Bluetooth (αυτό απαιτείται όταν χάσετε τη σύνδεση με το RileyLink και το σύστημα δεν μπορεί να ανακτήσει αυτόματα - συμβαίνει κατά διαστήματα). Έτσι πρέπει να πάρετε συσκευή με Android 6.0 - 8.1, στη χειρότερη περίπτωση μπορείτε να εγκαταστήσετε LinegaeOS 15.1 (απαιτείται 15.1 ή χαμηλότερη) στο τηλέφωνό σας. Εξετάζουμε το πρόβλημα με το Android 9, αλλά μέχρι στιγμής δεν έχουμε βρει λύση (φαίνεται ότι λειτουργεί σε μερικά μοντέλα και όχι σε άλλα).**
- ** RileyLink / Gnarl: ** Για επικοινωνία με την αντλία χρειάζεστε συσκευή που μετατρέπει τις εντολές BT από το τηλέφωνο σε RF εντολές που κατανοεί η αντλία. Η συσκευή που λέγεται RileyLink (μπορείτε να την πάρετε εδώ [ getrileylink.org ](https://getrileylink.org/)). Χρειάζεστε σταθερή έκδοση της συσκευής, η οποία είναι για τα παλαιότερα μοντέλα firmware 0.9 (παλαιότερες εκδόσεις μπορεί να μην λειτουργούν σωστά) ή για νεώτερα μοντέλα 2.2 (υπάρχουν επιλογές για αναβάθμιση διαθέσιμες στην τοποθεσία RL). Εάν νιώθετε περιπετειώδης, μπορείτε επίσης να δοκιμάσετε το Gnarl ([ εδώ ](https://github.com/ecc1/gnarl)), το οποίο είναι είδος του RileyLink-clone. 
- ** Αντλία: ** Το πρόγραμμα οδήγησης λειτουργεί μόνο με τα ακόλουθα μοντέλα και εκδόσεις υλικολογισμικού: 
    - 512/712
    - 515/715
    - 522/722
    - 523/723 (firmware 2.4A ή χαμηλότερη)
    - 554/754 Έκδοση ΕΕ (firmware 2.6A ή χαμηλότερη)
    - 554/754 Έκδοση Καναδά (firmware 2.7A ή χαμηλότερη)

## Διαμόρφωση της αντλίας

- ** Ενεργοποιήστε την απομακρυσμένη λειτουργία στην αντλία ** (Βοηθητικά προγράμματα -> Απομακρυσμένες επιλογές, επιλέξτε Ναι, και στην επόμενη οθόνη κάντε Προσθήκη ταυτότητας και προσθέστε ψεύτικη ταυτότητα (111111 ή κάτι τέτοιο). Πρέπει να έχετε τουλάχιστον ένα αναγνωριστικό στη λίστα απομακρυσμένων αναγνωριστικών. Αυτές οι επιλογές ενδέχεται να φαίνονται διαφορετικά σε διαφορετικό μοντέλο αντλίας. Αυτό το βήμα είναι σημαντικό, γιατί όταν ρυθμιστεί, η αντλία θα ακούει πιο συχνά για απομακρυσμένη επικοινωνία.
- ** Ρυθμίστε το μέγιστο βασικό** στην αντλία σας στο "εισαγωγή μεγίστου βασικού στο προφίλ STD" * 4 (αν θέλετε να έχετε 400% TBR ως μέγιστο). Αυτός ο αριθμός πρέπει να είναι κάτω από 35 (όπως μπορείτε να δείτε στην αντλία).
- ** Ορισμός μέγιστης δόσης ** στην αντλία σας (το μέγιστο είναι 25)
- ** Ρυθμίστε το προφίλ σε STD **. Αυτό θα είναι το μοναδικό προφίλ που θα χρησιμοποιήσουμε. Μπορείτε επίσης να απενεργοποιήσετε.
- ** Ορίστε τον τύπο TBR ** στο Απόλυτο (όχι επί της εκατό)

## Διαμόρφωση του τηλεφώνου / AndroidAPS

- ** Μην αντιστοιχίζετε το RileyLink με το τηλέφωνό σας. ** Αν έχετε αντιστοιχίσει το RileyLink, τότε το AndroidAPS δεν θα το βρει στη διαμόρφωση.
- Απενεργοποιήστε την Αυτόματη περιστροφή στο τηλέφωνό σας (σε ορισμένες συσκευές Αυτόματη περιστροφή επανενεργοποιεί τις περιόδους λειτουργίας BT, κάτι που δεν είναι κάτι που θα θέλαμε).
- Μπορείτε να ρυθμίσετε την αντλία στο AndroidAPS με δύο τρόπους: 

1. Χρήση του Οδηγού (σε νέα εγκατάσταση)
2. Απευθείας στην καρτέλα Config (εικονίδιο Cog στο πρόγραμμα οδήγησης της Medtronic)

Αν κάνετε νέα εγκατάσταση, θα πεταχτείτε απευθείας στον οδηγό. Μερικές φορές, εάν η σύνδεσή σας BT δεν λειτουργεί πλήρως (δεν μπορείτε να συνδεθείτε με την αντλία), ενδέχεται να μην μπορείτε να ολοκληρώσετε τη διαμόρφωση. Σε αυτή την περίπτωση επιλέξτε την εικονική αντλία και αφού ολοκληρωθεί ο οδηγός, μπορείτε να πάτε με την επιλογή 2, η οποία θα παρακάμψει την ανίχνευση της αντλίας.

![Ρυθμίσεις MDT](../images/Medtronic01.png)

Πρέπει να ορίσετε τα παρακάτω στοιχεία: (δείτε την παραπάνω εικόνα)

- ** Σειριακός αριθμός αντλίας **: Μπορείτε να βρείτε αυτό στην πίσω πλευρά, είσοδος SN. Πρέπει να πάρετε μόνο τα νούμερα, η σειρά σας είναι 6 αριθμοί.
- **Τύπος αντλίας**: Ποιο τύπο αντλίας έχετε (π.χ. 522). 
- ** Συχνότητα αντλίας **: Σύμφωνα με τη συχνότητα της αντλίας, πραγματοποιήθηκαν δύο εκδόσεις της αντλίας Medtronic (αν δεν είστε σίγουροι για τη συχνότητα που χρησιμοποιεί η αντλία σας, κοιτάξτε [ Συχνές ερωτήσεις ](../Configuration/MedtronicPump#faq)): 
    - για ΗΠΑ & Καναδά, η συχνότητα που χρησιμοποιείται είναι 916 Mhz
    - για παγκόσμια κλίμακα, η συχνότητα που χρησιμοποιείται είναι 868 Mhz
- ** Μέγιστο Bolus στην αντλία(U) ** (σε μια ώρα): Αυτό πρέπει να ρυθμιστεί στο ίδιο επίπεδο όπως και στην αντλία. Περιορίζει πόση ινσουλίνη μπορείτε να κάνετε με το Bolus. Εάν υπερβείτε αυτό, το Bolus δεν θα δοθεί και σφάλμα θα ηχήσει. Το μέγιστο που μπορεί να χρησιμοποιηθεί είναι 25, ορίστε τη σωστή τιμή για τον εαυτό σας εδώ, ώστε να μην κάνετε υπερβολική δόση.
- ** Μέγιστος βασικός στην αντλία (U / h) **: Αυτό πρέπει να ρυθμιστεί στο ίδιο επίπεδο όπως και στην αντλία. Περιορίζει πόση βασική μπορείτε να πάρετε σε μια ώρα. Έτσι, για παράδειγμα, εάν θέλετε να ρυθμίσετε το μέγιστο TBR στο 500% και το υψηλότερο των βασικών μοτίβων σας είναι 1,5 U, τότε θα πρέπει να ρυθμίσετε το Max Basal σε τουλάχιστον 7,5. Αν αυτή η ρύθμιση είναι λάθος (για παράδειγμα, αν ένα από τα βασικά μοτίβα σας υπερβεί αυτή την τιμή, η αντλία θα επιστρέψει σφάλμα).
- ** Καθυστέρηση πριν από την εκκίνηση του Bolus **: Αυτό είναι καθυστέρηση πριν από την αποστολή bolus στην αντλία, έτσι ώστε αν αλλάξετε γνώμη, μπορείτε να την ακυρώσετε. Η ακύρωση του bolus κατά τη χορήγηση του bolus δεν υποστηρίζεται από την αντλία (εάν θέλετε να σταματήσετε το bolus κατά τη διάρκεια της λειτουργίας, πρέπει να σταματήσετε την αντλία και στη συνέχεια να συνεχίσετε).
- ** Κωδικοποίηση Medtronic **: Αυτή είναι η ρύθμιση που καθορίζει αν η κωδικοποίηση 4b6b που κάνουν οι συσκευές της Medtronic θα γίνει στο AndroidAPS ή στο RileyLink. Αν έχετε RileyLink με firmware 2.x, η προεπιλεγμένη τιμή θα είναι να χρησιμοποιήσετε την κωδικοποίηση υλικού (= έγινε από RileyLink), αν έχετε 0.x firmware, αυτή η ρύθμιση θα αγνοηθεί.
- ** Τύπος μπαταρίας (Power View) **: Αν θέλετε να δείτε την ισχύ της μπαταρίας στην αντλία σας, πρέπει να επιλέξετε τον τύπο μπαταρίας που χρησιμοποιείτε (υποστηρίζεται προς το παρόν Lithium ή Alkaline) υπολογισμένο ποσοστό και βολτ.
- ** Διαμόρφωση RileyLink **: Θα βρείτε τη συσκευή σας RileyLink / GNARL.

## Καρτέλα MEDTRONIC (MDT)

![Καρτέλα MDT](../images/Medtronic02.png)

Στην καρτέλα αντλίας μπορείτε να δείτε αρκετές γραμμές που εμφανίζουν την τρέχουσα κατάσταση αντλιών (και συνδέσεων).

- ** Κατάσταση RileyLink **: Εμφανίζει την κατάσταση της σύνδεσης RileyLink. Το τηλέφωνο θα πρέπει να είναι συνεχώς συνδεδεμένο στο RileyLink.
- ** Κατάσταση αντλίας **: Κατάσταση σύνδεσης αντλίας, αυτό μπορεί να έχει πολλές τιμές, αλλά κυρίως θα δούμε εικονίδιο ύπνου (όταν η σύνδεση αντλίας δεν είναι ενεργή), όταν η εντολή εκτελείται, μπορεί να δείτε ''ξύπνημα'', το οποίο είναι το AAPS που προσπαθεί να κάνει σύνδεση με την αντλία σας ή την περιγραφή οποιασδήποτε εντολής που μπορεί να τρέχει στην αντλία (π. χ.: ρύθμισε ώρα, όρισε TBR, κλπ.).
- ** Μπαταρία **: Εμφανίζει την κατάσταση μπαταρίας ανάλογα με τη διαμόρφωσή σας. Αυτό μπορεί να είναι ένα απλό εικονίδιο που δείχνει εάν η μπαταρία είναι άδεια ή γεμάτη (κόκκινο εάν η μπαταρία είναι κρίσιμη, κάτω από 20%), ή ποσοστό και τάση.
- ** Τελευταία σύνδεση **: Ο χρόνος κατά τον οποίο η τελευταία σύνδεση με την αντλία ήταν επιτυχής.
- ** Τελευταία bolus **: Πότε δόθηκε το τελευταίο bolus.
- ** Κύριος βασικός ρυθμός **: Αυτός είναι ο κύριος βασικός ρυθμός που τρέχει στην αντλία αυτή την ώρα.
- ** Προσωρινός βασικός **: Προσωρινός βασικός που εκτελείται ή είναι άδειος.
- ** Δεξαμενή **: Πόση ινσουλίνη υπάρχει στη δεξαμενή (ενημερώνεται τουλάχιστον κάθε ώρα).
- ** Σφάλματα **: Η σειρά σφάλματος αν υπάρχει πρόβλημα (συνήθως δείχνει αν υπάρχει σφάλμα στη διαμόρφωση).

Στο κάτω άκρο έχουμε 3 κουμπιά:

- ** Ανανέωση ** προορίζεται για την ανανέωση της κατάστασης. Αυτό θα πρέπει να χρησιμοποιείται μόνο αφού η σύνδεση δεν υπήρχε εδώ και πολύ καιρό, καθώς αυτή η ενέργεια θα επαναφέρει δεδομένα σχετικά με την αντλία (ανάκτηση ιστορικού, λήψη / ρύθμιση ώρας, λήψη προφίλ, λήψη κατάστασης μπαταρίας κλπ.).
- ** Ιστορικό αντλίας **: Εμφανίζει το ιστορικό αντλίας (δείτε [ παρακάτω ](../Configuration/MedtronicPump#pump-history))
- ** Στατιστικά RL **: Εμφάνιση στατιστικών RL (δείτε [ παρακάτω ](../Configuration/MedtronicPump#rl-status-rileylink-status))

## Ιστορικό αντλίας

![Διάλογος ιστορικού αντλίας](../images/Medtronic03.png)

Το ιστορικό της αντλίας ανακτάται κάθε 5 λεπτά και αποθηκεύεται τοπικά. Διατηρούμε το ιστορικό μόνο για τις τελευταίες 24 ώρες, έτσι οι παλαιότερες καταχωρήσεις καταργούνται όταν προστίθενται νέες. Αυτός είναι ένας απλός τρόπος για να δείτε το ιστορικό της αντλίας (ορισμένες καταχωρίσεις από την αντλία ενδέχεται να μην εμφανίζονται, επειδή δεν είναι σχετικές - για παράδειγμα, διαμόρφωση λειτουργιών που δεν χρησιμοποιούνται από το AndroidAPS).

## Κατάσταση RL (κατάσταση RileyLink)

![Κατάσταση RileyLink - Ρυθμίσεις](../images/Medtronic04.png) ![Κατάσταση RileyLink - Ιστορικό](../images/Medtronic05.png)

Το παράθυρο διαλόγου έχει δύο καρτέλες:

- ** Ρυθμίσεις **: Εμφανίζει τις ρυθμίσεις για το RileyLink: Διαμορφωμένη διεύθυνση, συνδεδεμένη συσκευή, κατάσταση σύνδεσης, σφάλμα σύνδεσης και εκδόσεις firmware RileyLink. Ο τύπος συσκευής είναι πάντα η αντλία Medtronic, το μοντέλο θα είναι το μοντέλο σας, ο σειριακός αριθμός έχει διαμορφωθεί στον σειριακό αριθμό, η συχνότητα αντλίας δείχνει τη συχνότητα που χρησιμοποιείτε, η τελευταία συχνότητα είναι η τελευταία χρησιμοποιούμενη συχνότητα.
- ** Ιστορικό **: Εμφανίζει το ιστορικό επικοινωνίας, τα στοιχεία με το RileyLink δείχνει αλλαγές κατάστασης για το RileyLink και το Medtronic δείχνει ποιες εντολές έχουν σταλεί στην αντλία.

## Ενέργειες

Όταν είναι επιλεγμένο το πρόγραμμα οδήγησης της Medtronic, μπορούν να προστεθούν 3 ενέργειες στην καρτέλα Ενέργειες:

- **Wake and Tune Up ** - Εάν δείτε ότι το AndroidAPS σας δεν έρχεται σε επαφή με την αντλία σας κάποια στιγμή (πρέπει να επικοινωνήσετε με αυτό κάθε 5 λεπτά), μπορείτε να εξαναγκάσετε τη ρύθμιση Tune Up. Αυτό θα προσπαθήσει να επικοινωνήσει με την αντλία σας, αναζητώντας όλες τις δευτερεύουσες συχνότητες στις οποίες μπορεί να επικοινωνήσει η αντλία. Αν βρίσκει κάποια, θα την ορίσει ως την προεπιλεγμένη συχνότητα. 
- ** Επαναφορά του RileyLink Config ** - Εάν επαναφέρετε το RileyLink / GNARL, πρέπει να χρησιμοποιήσετε αυτήν την ενέργεια, έτσι ώστε να είναι δυνατή η αναδιάρθρωση της συσκευής (ρύθμιση συχνότητας, ρύθμιση τύπου συχνότητας, ρύθμιση παραμέτρων κωδικοποίησης).
- ** Εκκαθάριση αποκλεισμού bolus ** - Όταν ξεκινάτε το bolus, ρυθμίζουμε το Bolus Block, το οποίο εμποδίζει την έκδοση οποιασδήποτε εντολής για την αντλία. Αν αναστείλετε την αντλία σας και συνεχίσετε (για να ακυρώσετε το bolus), μπορείτε να καταργήσετε αυτό το μπλοκ. Η επιλογή υπάρχει μόνο όταν εκτελείται bolus... 

## Σημαντικές σημειώσεις

### Καταγραφή

Εφόσον το πρόγραμμα οδήγησης της Medtronic είναι πολύ καινούργιο, πρέπει να ενεργοποιήσετε την καταγραφή, ώστε να εντοπίσουμε τα λάθη και να διορθώσουμε τα προβλήματα, αν αυτά προκύψουν. Κάντε κλικ στο εικονίδιο στην επάνω αριστερή γωνία, επιλέξτε Συντήρηση και Ρυθμίσεις καταγραφής. Οι επιλογές αντλίας, επικοινωνία αντλίας, επικοινωνία BT αντλίας πρέπει να ελεγχθούν.

### RileyLink/GNARL

Όταν κάνετε επανεκκίνηση του RileyLink ή του GNARL, πρέπει είτε να κάνετε νέα ρύθμιση ''TuneUp'' (ενέργεια "Ξυπνήστε και συντονίστε") είτε να ξαναστείλετε τις παραμέτρους επικοινωνίας (ενέργεια "Reset RileyLink Config"), διαφορετικά η επικοινωνία θα αποτύχει.

### CGMS

Το Medtronic CGMS δεν υποστηρίζεται επί του παρόντος.

### Χειροκίνητη χρήση της αντλίας

Θα πρέπει να αποφύγετε χειροκίνητα την επεξεργασία θεμάτων στην αντλία σας. Όλες οι εντολές (bolus, TBR) θα πρέπει να περάσουν από το AndroidAPS, αλλά εάν συμβεί να κάνετε χειροκίνητες εντολές, ΔΕΝ χρησιμοποιείτε εντολές με συχνότητα μικρότερη από 3 λεπτά (έτσι εάν κάνετε 2 bolus (για οποιοδήποτε λόγο) το δεύτερο πρέπει να είναι τουλάχιστον 3 λεπτά μετά το πρώτο).

## Αλλαγές ζώνης ώρας και DST (Daylight Saving Time) ή Ταξιδεύοντας με την αντλία Medtronic και το AndroidAPS

Σημαντικό πράγμα που πρέπει να θυμάστε είναι ότι δεν πρέπει ποτέ να απενεργοποιήσετε το κύκλωμα όταν ταξιδεύετε (εκτός αν το CGMS σας δεν μπορεί να κάνει λειτουργία εκτός σύνδεσης). Το AAPS θα ανιχνεύσει αυτόματα τις αλλαγές ζώνης ώρας και θα στείλει εντολή στην αντλία για να αλλάξει το χρόνο, όταν αλλάξει ο χρόνος στο τηλέφωνο.

Τώρα αν ταξιδεύετε στην Ανατολή και οι αλλαγές της ζώνης ώρας αλλάζουν σας προσθέτοντας ώρες (π. χ. από GMT + 0 έως GMT + 2), το ιστορικό αντλιών δεν θα έχει πρόβλημα και δεν χρειάζεται να ανησυχείτε... αλλά αν ταξιδέψετε Δυτικά και οι αλλαγές της ζώνης ώρας γίνονται με την αφαίρεση ωρών (GMT + 2 έως GMT-0), τότε ο συγχρονισμός μπορεί να είναι μικρός. Με απλά λόγια, αυτό σημαίνει ότι για τις επόμενες x ώρες θα πρέπει να είστε προσεκτικοί, επειδή το IOB σας, μπορεί να είναι λίγο περίεργο.

Γνωρίζουμε αυτό το πρόβλημα και ήδη ψάχνουμε για μια πιθανή λύση (βλ. Https://github.com/andyrozman/RileyLinkAAPS/issues/145), αλλά προς το παρόν έχετε υπόψη σας αυτές τις πληροφορίες όταν ταξιδεύετε.

## Συχνές ερωτήσεις

### Μπορώ να δω τη δύναμη του RileyLink / GNARL;

Όχι. Προς το παρόν καμία από αυτές τις συσκευές δεν το υποστηρίζει αυτό και μάλλον δεν θα το κάνει στο μέλλον.

### Είναι το GNARL πλήρης αντικατάσταση για το RileyLink;

Ναι. Ο συγγραφέας του GNARL πρόσθεσε όλες τις λειτουργίες που χρησιμοποιεί ο οδηγός της Medtronic. Υποστηρίζεται όλη η επικοινωνία της Medtronic (τη στιγμή της σύνταξης (Ιούνιος / 2019). Το GNARL δεν μπορεί να χρησιμοποιηθεί για επικοινωνία Omnipod. Το μειονέκτημα του GNARL είναι ότι πρέπει να το φτιάξετε μόνοι σας και πρέπει να έχετε συμβατή έκδοση υλικού.

** Σημείωση από συντάκτη: ** Λάβετε υπόψη ότι το λογισμικό GNARL εξακολουθεί να είναι πειραματικό και ελαφρώς δοκιμασμένο και δεν πρέπει να θεωρείται ασφαλές ως RileyLink.

### Πού μπορώ να βρω το RileyLink ή το GNARL;

Όπως προαναφέρθηκε μπορείτε να πάρετε συσκευές εδώ:

- RileyLink - Μπορείτε να πάρετε τη συσκευή εδώ - [ getrileylink.org ](https://getrileylink.org/).
- GNARL - Μπορείτε να λάβετε πληροφορίες εδώ, αλλά η συσκευή πρέπει να παραγγελθεί αλλού ([ github.com/ecc1/gnarl ](https://github.com/ecc1/gnarl)).

### Τι πρέπει να κάνω εάν χάσω τη σύνδεση με το RileyLink ή / και την αντλία;

1. Εκτελέστε τη λειτουργία "Ξυπνήστε και συντονίστε", αυτή θα προσπαθήσει να βρει τη σωστή συχνότητα για να επικοινωνήσει με την αντλία.
2. Απενεργοποιήστε το Bluetooth, περιμένετε 10 δευτερόλεπτα και ενεργοποιήστε το ξανά. Αυτό θα αναγκάσει την επανασύνδεση με το RileyLink.
3. Επαναφέρετε το RileyLink, αφού το κάνετε αυτό, μην ξεχάσετε να εκτελέσετε τη διαδικασία "Επαναφορά διαμόρφωσης RileyLink ".
4. Δοκιμάστε 3 και 2 μαζί.
5. Επαναφέρετε το RileyLink και επαναφέρετε το τηλέφωνο.

### Πώς να καθορίσετε ποια συχνότητα χρησιμοποιεί η αντλία σας

![Μοντέλο αντλίας](../images/Medtronic06.png)

Εάν γυρίσετε την αντλία σας στην πρώτη γραμμή στη δεξιά πλευρά θα δείτε ειδικό κωδικό 3 γραμμάτων. Τα πρώτα δύο γράμματα καθορίζουν τον τύπο συχνότητας και το τελευταίο προσδιορίζει το χρώμα. Εδώ είναι πιθανές τιμές για τη συχνότητα:

- ΒA - Βόρεια Αμερική (στην επιλογή συχνότητας πρέπει να επιλέξετε "ΗΠΑ & Καναδάς (916 MHz)")
- ΚA - Καναδάς (στην επιλογή συχνότητας πρέπει να επιλέξετε "ΗΠΑ & Καναδάς (916 MHz)")
- ΠΑ - Παγκοσμίως (στην επιλογή συχνότητας πρέπει να επιλέξετε "Σε όλο τον κόσμο (868 Mhz)")