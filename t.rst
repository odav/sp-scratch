
test hete with ``code`` and  **gsgxx**



.. code-block:: java

   // Load management
   List<UniManagement> m = UniManagement.from(management);

 // create sequence
 List<UniEvent> uEvents = UniManagement.createEventSequence(m, start.getYear(), end.getYear());

 // check for correct event dates in sequence
 UniEvent.checkEventDates(uEvents, start, end);

 try (SwatPlusDomainDB db = SwatPlusDomainDB.create(resources().getJDBC(SP_DB))) {
   // map UE to SPE

   SwatPlusManagement spm = SwatPlusManagement.from(uEvents, "mgt_01", db);
   spm.writeFiles(workspace().getDir(), scenario);
 }

ss

* here
* more
