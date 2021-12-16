Developer options
=================

Options useful mostly for developers of Genozip:

Usage: as flags for ``genozip`` (Z), ``genounzip`` (U), ``genocat`` (C), ``genols`` (L)

*Note*: When used with ``genocat`` most options show only the requested metadata and not the file data itself.

**Memory consumption**

.. option:: --show-memory  ZUCL. Show what buffers are consuming the most memory.

          |

.. option:: kill -USR1 <pid>.  ZUCL. Executes --show-memory on a running process. Not available on Windows.

          |

.. option:: --debug-memory[=bytes]  ZUCL. Show Buffer allocations and destructions. If <bytes> is specified then show only allocations of at least <bytes>.

          |

.. option:: --show-hash  Z. See raw numbers that feed into determining the size of the global hash tables.

          |

**genozip file contents**

.. option:: --show-alleles  ZUC. (VCF only) Output allele values to stdout. Each row corresponds to a row in the VCF file. Mixed-ploidy regions are padded and 2-digit allele values are replaced by an ascii character.

          |

.. option:: --show-dict[=field]  ZUC. Show dictionaries read/written for each vblock. With optional <field> (use --STATS to see the field names in the file) shows only that one field. 

          |

.. option:: --show-counts=field  ZUC. Show (per snip in dictionary) the number of words in the file using this snip. genozip - works for any context (use --STATS to see context names). genounzip/genocat - works only for contexts that have a SEC_COUNTS section (which include any contexts in a file generated with genozip --show-counts of that context). 

          |

.. option:: --show-b250=field  ZUC. Show b250 sections content - each value shows the line (counting from 1) and the index into its dictionary (note: REF and ALT are compressed together as they are correlated). With optional <field> (eg CHROM ; RNAME ; POS ; AN etc) shows only that one field. This also works with genounzip and genocat but without the line numbers. 

          |

.. option:: --dump-b250=field.  ZUC.  Dump the binary content of the b250 data of this field exactly as they appear in the genozip format to a file named "<field>.b250" - specify the field name as it appears in the "Name" column in --SHOW-STATS for fields that have "comp b250" data. 

          |

.. option:: --dump-local=field.  ZUC.  Same as --dump-b250 just for the "local" buffer.

          |

.. option:: --contigs.  ZUC.  List the names of the chromosomes (or contigs) included in the file. Alternative names: --chroms --list-chroms

          |

.. option:: --dump-section section-type.  ZUC. Dump the uncompressed unencrypted contents of all sections of this type (as it appears in --show-gheaders eg SEC_REFERENCE) to a files named "<section-type>.<vb>.<dict_id>.[header|body]".

          |

.. option:: --show-headers section-type.  ZUC. Show all the sections headers or those of a specific section type if the optional argument is provided. Argument is a case-insesitive substring of a section name.

          |

.. option:: --show-index  ZUC. Show the content of the random access index (SEC_RANDOM_ACCESS section). 

          |

.. option:: --show-reference  ZUC. Show the ranges included the SEC_REFERENCE sections

          |

.. option:: --show-ref-seq  ZUC. Show the reference sequences as stored internally in a SAM BAM or FASTQ file (also works for a reference file but --reference --regions is faster). Combine with --regions to see specific regions (genocat only). Combine with --sequential to omit newlines. '-' appears in unset loci.

          |

.. option:: --show-ref-diff  C. Show the difference between two reference files. Use in combination with two --reference arguments.

          |

.. option:: --show-ref-index  ZUC. Show the content of the random access index of the reference data (SEC_REF_RAND_ACC section).

          |

.. option:: --show-ref-hash  ZUC. Show the details of the reference hash table (SEC_REF_HASH) sections. 

          |

.. option:: --show-chrom2ref  ZUC. Show the details of the file contigs that are mapped to a different contig name in the reference (eg '22' ➔ 'chr22'). 

          |

.. option:: --show-ref-contigs  ZUC. Show the details of the reference contigs. 

          |

.. option:: --show-ref-iupacs  ZC. Show the the IUPACs in the reference. In combination with genozip --chain - also shows the VCF variants that have a IUPAC in the Luft reference and how they are handled.

          |

.. option:: --show-kraken  C. Show inclusion or exclusion of lines. Used in combination with --taxid.

          |

.. option:: --show-txt-contigs  ZUC. (SAM and BAM) Show the details of the contigs appearing the file header (SQ lines). 

          |

.. option:: --show-gheader  ZUC.  Show the content of the genozip header (which also includes the list of all sections in the file). 

          |

.. option:: --show-vblocks  ZUC.  Show vblock headers as they are read / written.

          |

.. option:: --show-aliases  ZUC. See contents of SEC_DICT_ID_ALIASES section.

          |

.. option:: --show-reference  ZUC. Show the ranges included the SEC_REFERENCE sections.

          |

.. option:: --show-is-set contig.  UC. Shows the contents of SEC_REF_IS_SET section for the given contig.

          |

.. option:: --show-bgzf  ZUC. Show BGZF blocks as they are being compressed or decompressed.

          |

.. option:: --show-dvcf  C. Show line-by-line outcome of the liftover of that line. Used with dual-coordinate files and may be combined --luft.

    | See: :ref:`dvcf`
    |

.. option:: --biopsy=vb,vb...  C. Dump a subset VBs of the source file being compressed and including the txt header. The argument is a comma separated list of VB numbers or VB ranges.

    | Example: ``genozip mybam.bam --biopsy 5-7,11`` will emit the txt header and VBs 5,6,7,11.
    |


**Tracking execution**

.. option:: --show-containers[=field]  ZUC. Show flow of containers. Possibly with the values of a specific field (use --STATS to see the field names in the file).

          |

.. option:: --show-threads  ZUC.  Show thread dispatcher activity.

          |

.. option:: --debug-threads  ZUCL.  Alternative to --show-threads - store thread log in a buffer and display it in case of an error.

          |

.. option:: --debug-seg[=field]  Z.  Shows snips being segmented into contexts - possibly limiting to a specific field (use --STATS to see the field names in the file).

          |

.. option:: --count=VB  CU. Show number of lines written for each VBlock (note: --count without an argument shows lines written in the entire file).

          |

.. option:: --debug-progress  ZUC. See raw numbers that feed into the progress indicator.

          |
.. option:: --debug-stats  Z. See details in the creation process of the --stats report.

          |

.. option:: --debug-generate  Z. See contexts that are marked as "all the same" and are removed or shrunk.

          |

.. option:: --debug-recon-size  Z. See vb->context[]->txt_len and vb->recon_size.

          |

.. option:: --show-time=res. ZUCL. Show what functions are consuming the most time. Optional <res> is one of the members of ProfilerRec defined in profiler.h such 'compressor_lzma' or a substring such as 'compressor_'.

          |

.. option:: --show-digest  ZUC. Show digest (MD5 or Adler32) updates.

          |

.. option:: --show-mutex[=mutex-name].  ZUC. Shows locks and unlocks of all mutexes or a particular mutex.

          |

.. option:: --show-uncompress.  ZUC. Shows uncompressing of section data.

          |

.. option:: --show-flags.  ZUCL. Shows internal flags after initialization.

          |

.. option:: --show-recon.  UC. Shows the reconstruction plan.

          |

.. option:: --show-dvcf.  C. When used with dual-coordinate VCF file shows for each variant its Coordinates (Primary Luft or Both) and its oStatus.

          |

.. option:: --show-wrong-md.  C. SAM with MD:Z field - shows cases where the special MD algorithm is not applied to the MD:Z in the data

          |

.. option:: --debug-LONG.  C. SAM/BAM and FASTQ: treat data as long reads regardless of the actual read length

          |

**Tracking compression performance**

.. include:: opt-stats.rst

.. option:: --show-codec  Z. Genozip tests for the best codec when it first encounters a new type of data. See the results.

          |

.. option:: --verify-codec  ZUC. Verifies each section's decompression correctness against an Adler32 that is stored in SectionHeader.magic. Note: the Genozip file generated when using this option is not a valid Genozip file as it has the wrong magic - this option is designed for detecting issues while developing new codecs.

    | Example: ``genozip -t --verify-codec myfile.sam``
    |

**Controlling execution**

.. option:: --one-vb vb  C. Reconstruct data from a single VB.

          |

.. option:: --seg-only  Z. Run the segmenter but don't compress and don't write the output.

          |

.. option:: --xthreads  ZUC. Use only one thread for the main PIZ/ZIP dispatcher. This doesn't affect thread use of other dispatchers.

          |


