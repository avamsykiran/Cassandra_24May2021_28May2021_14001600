
Cassandra
-----------------------------------------------

    a NOSQL database....

    document refers to object-as-file

    RDBMS                   NOSQL
    --------------------------------------------------------------------
    Powerful Qry Lang       Simple Qry Lang

    Support Txns            No Txns are supported

    ACID, for consistency   The design favours data consistency...

    Atomicity
    Consistency
    Integrity
    Durability

    Cassandra Eco System
    ---------------------------------------------------------------------

            Support Huge Work Laods
            
            Distributed System.

            Clustur:
                    is a distributed system
                    of nodes, so connected that
                    can process collectivly
                    and distributedly, though
                    being in a isolated env.,

            Replication:
                    storing the data 
                    repeatdly on each node
                    of the clustur.

                    This support high
                        Availability
                        Scalability.

            Clustur ---------->
                                    Data Center  --------->
                                                            Nodes

            Reliability/Durabilit:
                                    Commit-log
                                            Eacn and every write operation
                                            is logged.

            Mem-Table           a datastructure that models our docvuemtns
            SSTable             a model inwhicht he data is written to the disk.
            bloom filter        algorithm follwoed to keep the SSTable and MemTable in sync.

            CQL
            --------------------------------------------------------

                Cassandra Qry Language.

                CQLSH   Cassandra Query Shell
                        is the interface used by database developers 
                        to access cassandra.


            Installing Cassandra
            ===============================================
            1. JDK 1.7 or above
            2. Python 2.7
            3. downlaod and extract apache cassandra

                (a) start cassandra.bat
                (b) start cqlsh.bat

          Data Types
          -----------------------------------------
          ascii
          bigint
          blob
          boolean
          counter
          decimal
          double
          float
          tuple
          inet
          int
          list
          map
          set
          text
          timestamp
          varchar
          varint

          Data Model
          ------------------------------------------------------------------

          Clustur ---------->
                                    Data Center  --------->
                                                            Nodes

                Keyspace
                                Replication Factor              the number of copies of each keyspace to maintian

                                Replication Strategy:
                                                1. Simple Strategy               rack-aware strategy
                                                2. old netwrok topology          rack-aware strategy
                                                3. network topology strategy     data-center aware strategy

                Keyspace = one or more column families 
                   column family = one or more rows
                         row = a collection of ordered columns

                1. Does not support join, aggregates, grouping, or clause
                2. miximized the data duplication.


                CQL - Cassandra Query Language
                ================================================================================================

                  Keyspaces
                  -------------------------------------------------------------------------------------
                        CREATE KEYSPACE keySpaceName WITH proeprties

                        CREATE KEYSPACE ks1 WITH replication={'class':'SimpleStrategy','replication_factor':2};

                        DESCRIBE keyspaces;

                        USE keySpaceName;

                        ALTER KEYSPACE keySpaceName WITH proeprties

                        ALTER KEYSPACE ks1 WITH replication={'class':'NetworkStrategy','replication_factor':3};

                        DROP KEYSPACE keySpaceName;

                
                  Column Families / Tables
                  ----------------------------------------------------------------------------------------

                        CREATE COLUMNFAMILY|TABLE tableName (
                                colsName        dataType        PRIMARY KEY,
                                colName         dataType
                                ...................................
                        );

                        CREATE COLUMNFAMILY|TABLE tableName (
                                colsName        dataType  ,
                                colName         dataType
                                ...................................
                                PRIMARY KEY (col1,col2)
                        );


                        CREATE TABLE Books (
                                bcode int primary key,
                                title text,
                                author text,
                                price varint,
                                copies  int
                        );

                        ALTER TABLE tableName ADD colName datatype
                        ALTER TABLE tableName DROP colName
                        ALTER TABLE tableName DROP (col1,col2)

                        ALTER TABLE Books ADD subject text;
                        ALTER TABLE Books ADD category text;

                        ALTER TABLE Books DROP subject;

                        DESCRIBE COLUMNFAMILIES;

                        DROP TABLE tableName;

                        DROP TABLE Books;

                        TRUNCATE tableName;

                        



        
                











            







