# Gem5-Arch2
Ελευθεριάδης Ανδρέας Ευστάθιος 9649  
Κωτούλας Εμμανουήλ 9697  

### Βήμα 1ο  
    1.a.   
bzip :  
Commited instructions (system.cpu.committedInsts) : 100000001  
Executed instructions (sim_insts) : 100000001  
  
  mcf  :  
  Commited instructions (system.cpu.committedInsts) : 100000001  
  Executed instructions (sim_insts) : 100000001  
    
  hmmer :  
  Commited instructions (system.cpu.committedInsts) : 100000000  
  Executed instructions (sim_insts) : 100000000  
    
  sjeng :  
  Commited instructions (system.cpu.committedInsts) : 100000000  
  Executed instructions (sim_insts) : 100000000  
    
  libm :  
  Commited instructions (system.cpu.committedInsts) :    
  Executed instructions (sim_insts) :   
  
  Γιατί τα committed instructions δεν είναι ίσα με τα executed instructions?  
    
  Δεν φαίνεται διαφορά μεταξύ των commited και executed instructions.  
  Αν επιλέξαμε λάθος μετρική για τα Executed instructions. Θα περιμέναμε τα executed να είναι περισσότερα. Αυτό θα συνέβαινε γιατί ο CPU εκτελεί εντολές με βάση predictions για να γλιτώσει χρόνο, όταν περιμένει για να εκτελέσει άλλες εντολές και στην περίπτωσή που το prediction είναι λάθος, απορίπτει τα αποτελέσματα των εντολών.  
    
      
     1.b.  
  bzip :  
  Block replacements l1 data cache (system.cpu.dcache.replacements) : 710569  
  
  mcf  :  
  Block replacements l1 data cache (system.cpu.dcache.replacements) : 54452  
    
  hmmer :  
  Block replacements l1 data cache (system.cpu.dcache.replacements) : 65718  
    
  sjeng :  
  Block replacements l1 data cache (system.cpu.dcache.replacements) : 5262377    
    
  libm :  
  Block replacements l1 data cache (system.cpu.dcache.replacements) :   
     
       
    1.c.  
  bzip :  
  L2 cache acesses (system.l2.overall_accesses::total) : 712341  
  
  mcf  :  
  L2 cache acesses (system.l2.overall_accesses::total) : 724390 
    
  hmmer :  
  L2 cache acesses (system.l2.overall_accesses::total) : 70563  
    
  sjeng :  
  L2 cache acesses (system.l2.overall_accesses::total) : 5264051    
    
  libm :  
  L2 cache acesses (system.l2.overall_accesses::total) :  1488538

Σε περίπτωση που το gem5 δεν μας έδινε αυτήν
την πληροφορία, πώς θα μπορούσαμε να τα υπολογίσουμε από τα υπόλοιπα metrics του
gem5?  

  ?????? Δεν ξέρω. Αν αθροίσουμε όλα τα άλλα misses της L2;    
    
    
    2.(i)  
  bzip :  
  Runtime (sim_seconds) : 0.083982  
  
  mcf  :  
  Runtime (sim_seconds) : 0.064955  
    
  hmmer :  
  Runtime (sim_seconds) : 0.059396  
    
  sjeng :  
  Runtime (sim_seconds) : 0.513528      
    
  libm :  
  Runtime (sim_seconds) : 0.174671   
  
    2.(ii)  
  bzip :  
  CPI (system.cpu.cpi) :  1.679650  
  
  mcf  :  
  CPI (system.cpu.cpi) :  1.299095 
    
  hmmer :  
  CPI (system.cpu.cpi) : 1.187917  
    
  sjeng :  
  CPI (system.cpu.cpi) : 10.270554    
    
  libm :  
  CPI (system.cpu.cpi) : 3.493415   
  
    
    2.(iii)   
  bzip :  
  L1D miss rate (system.cpu.dcache.overall_miss_rate::total) : 0.014798  
  L1I miss rate (system.cpu.icache.overall_miss_rate::total) : 0.000077  
  L2 miss rate (system.l2.overall_miss_rate::total ) : 0.282163  
  
  mcf  :  
  L1D miss rate (system.cpu.dcache.overall_miss_rate::total) : 0.002108  
  L1I miss rate (system.cpu.icache.overall_miss_rate::total) : 0.023612  
  L2 miss rate (system.l2.overall_miss_rate::total ) : 0.055046  
    
  hmmer :  
  L1D miss rate (system.cpu.dcache.overall_miss_rate::total) : 0.001637 
  L1I miss rate (system.cpu.icache.overall_miss_rate::total) : 0.000221  
  L2 miss rate (system.l2.overall_miss_rate::total ) : 0.077760  
    
  sjeng :  
  L1D miss rate (system.cpu.dcache.overall_miss_rate::total) : 0.121831  
  L1I miss rate (system.cpu.icache.overall_miss_rate::total) : 0.000020  
  L2 miss rate (system.l2.overall_miss_rate::total ) : 0.999972  
    
  libm :  
  L1D miss rate (system.cpu.dcache.overall_miss_rate::total) : 0.060972     
  L1I miss rate (system.cpu.icache.overall_miss_rate::total) : 0.000094     
  L2 miss rate (system.l2.overall_miss_rate::total ) : 0.999944    
  
    
 Φτιάξτε γραφήματα που να απεικονίζουν αυτές τις πληροφορίες για το σύνολο των benchmarks. Τι παρατηρείτε;  
 
  Μεγάλα miss rate στις data caches αντιστοιχούν σε μεγάλα CPI και συνεπώς χειότερες επιδόσεις. Τα misses στην L1I δεν φαίνεται να επηρεάζουν ιδιαίτερα το CPI.  
  
    3. DEFAULT(2 Ghz)  
  bzip :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 500  
  sim_seconds : 0.064955 
    
  mcf  :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 500  
  sim_seconds : 0.059396  
    
  hmmer :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 500  
  sim_seconds : 0.059396
    
  sjeng :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 500  
  sim_seconds : 0.513528    
    
  libm :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 500  
  sim_seconds : 0.17467  
    
      
      3. 1.5 Ghz  
  bzip :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 667  
  sim_seconds : 0.109754 
    
  mcf  :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 667  
  sim_seconds : 0.086162
  
    
  hmmer :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 667  
  sim_seconds : 0.079149
    
  sjeng :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 667  
  sim_seconds : 0.581937    
    
  libm :  
  system.clk_domain.clock : 1000  
  cpu_cluster.clk_domain.clock (system.cpu_clk_domain.clock) : 667  
  sim_seconds : 0.205034 
  
  Μπορείτε να εξηγήσετε τελικά τι χρονίζεται στα 1,5GHz και τι χρονίζεται στα default GHz;   
  Το cpu clock, ενώ το system clock μένει σταθερό.  

Αναζητώντας πληροφορίες για το ρολόι, μπορείτε να δώσετε μια πιο σαφή απάντηση;   
???????????Ξερω γω    

Αν προσθέσουμε άλλον έναν επεξεργαστή, ποια εικάζετε ότι θα είναι η συχνότητα του;  
Ίδια με το cpu clock που ορίζουμε  

Υπάρχει τέλειο scaling; Μπορείτε να δώσετε μια εξήγηση αν δεν υπάρχει τέλειο scaling;  
Τα benchmarks bzip, mcf και hmmer που έχουν χαμηλά memory miss rates και συνεπώς CPI ~ 1 κάνουν scale γραμμικά και συνεπώς η μείωση του cpu clock έχει άυξηση χρόνου κατά περίπου το ίδιο ποσοστό.  
Τα benchmark sjeng και libm έχουν υψηλά memory miss rates και συνεπώς CPI πολύ μεγαλύτερα του 1 και συνεπώς η διαφορά στο cpu clock δεν έχει αντίστοιχη ποσοστιακή αύξηση του απαιτούμενου χρόνου.  

### Βήμα 2ο


### Βήμα 3ο



