2025-08-04 13:46

Tags: [[SQL]]

------------------------------------------------

#### Syntax:

CREATE TABLE ´fleet´ (
	id int NOT NULL AUTO_INCREMENT PRIMARY KEY,                   <-- common convention, unique identifier (primary key), cannot be empty (returns error), goes up for new vals automatically (auto_increment) 
	 company_id INT,                                                                                    <-- creates column that accepts int as values
	 FOREIGN KEY (company_id) REFERENCES company(id)             <-- assigns (/"mounts") column company_id to column "id" of table "company" 
	 (--> if the specified id at creation is not in the mounted column, it returns an error)
		 ON DELETE CASCADE                                           <-- when the referenced company_id is deleted, this entry kills itself. (Alternative: ON DELETE SET NULL -> removes reference or "mount" from table)
		 ON UPDATE CASCADE                                           <-- when the referenced company_id is changed, this entry kills itself. (see above)
	 //OPTIONAL (and automatically generated): 
	 KEY ´company_id´ (´company_id´)                         <-- redefines company_id as a key to make searching for it more efficient (idk why)
     //GENERATED AUTOMATICALLY:
     CONSTRAINT ´{internal name}´ FOREIGN KEY ´{key name ( as above )}´ REFERENCES ´{mounted table name} ({mounted key name})´ ON DELETE CASCADE ON UPDATE CASCADE // as above;
     // add these if you forgot them in the inital setup, adding is done via the command below
);

#### Additions: 

###### show create table fleet;
--> returns the above explained create statement for the specified table (here: fleet)

###### alter table fleet add {feature};
--> changes the table above to add the specified feature. The feature can be any of the ones valid above

**alter table fleet drop {feature};**
--> removes the feature, can be any of the above


------------------------------------------------------
### References
