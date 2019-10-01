The CTAT genome lib plug-n-play data libraries included database index files that may be architecture or operating-system specific.  They tend to work 'out of the box' with many versions of linux, but not other systems such as Mac.  In this case, you just need to rebuild the database indexes on your system.  This can be done by running the following command:

```
    # first change directory to your ctat genome lib dir:
    % cd /path/to/your/ctat_genome_lib_build_dir

    # then rebuild your indices like so:
    % ${STAR_Fusion_BASEDIR}/ctat-genome-lib-builder/util/rebuild_indices.pl .  #don't forget that final dot!

```

After the above works without error, you should be ready to run STAR-Fusion again.

>Note, this functionality is available as of STAR-Fusion v1.8.0

The above does require that you have STAR-Fusion software prerequisites such as the [Perl library DB_File](https://perldoc.perl.org/DB_File.html) installed.

If you are using our [STAR-Fusion Singularity image](https://github.com/STAR-Fusion/STAR-Fusion/wiki#Singularity), then you can simply run:

 ```
    # first change directory to your ctat genome lib dir:
    % cd /path/to/your/ctat_genome_lib_build_dir

    # then rebuild your indices like so:
    % singularity exec -e STAR-Fusion.simg \
       /usr/local/src/STAR-Fusion/ctat-genome-lib-builder/util/rebuild_indices.pl .  #don't forget that final dot!

```