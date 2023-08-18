It is **enabled at the bucket level**. Same key overwritewill increment the “version”: 1, 2, 3....

Once you version-enable a bucket, it can never return to an unversioned state. Versioning can  
only be suspended once it has been enabled. Suspending versioning does not delete the  
previous versions.

Any file that is not versioned prior to enabling versioning will have version “null”.