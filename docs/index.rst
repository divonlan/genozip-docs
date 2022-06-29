..
   (C) 2020-2022 Genozip Limited. All rights reserved.

Genozip
=======

*A universal genomic file compressor - for BAM, FASTQ, VCF and other genomic files*
            
Genozip is a universal compressor for genomic files - :ref:`FASTQ <fastq>`, :ref:`BAM/CRAM <bam>`, :ref:`VCF <vcf>` and :ref:`many other file formats <data-types>` (including non-genomic files). 

For Illumina data ``.bam`` and ``.fastq.gz`` files, the typical gain over gzip is around 4X. For PacBio and Oxford Nanopore data aligned ``.bam`` files, the gain is typically around 2X. For ``.vcf.gz`` files, the gain over gzip is typically 3-6X. Here are some :ref:`examples <benchmarks>`.

**Yes**, Genozip can compress already-compressed files (.gz .bz2 .xz .bam .cram).

The compression is **lossless** - the decompressed file is 100% identical to the original file (some :ref:`exceptions<losslessness>` apply).

Genozip consists of four command line tools:
  
   * :doc:`genozip` compresses files
  
   * :doc:`genounzip` decompresses files

   * :doc:`genols` shows metadata of compressed files and directories

   * :doc:`genocat` is the workhorse for using genozip in analytical pipelines:
      - Display the contents of a compressed file
      - Subset a compressed file - show a specific part of its contents
      - Translate a compressed file to another format (eg BAM to FASTQ)
      - Analyze a compressed file (eg showing the :ref:`sex<sex>` or :ref:`coverage<coverage>`)
  
|
 
.. include:: installing.rst

License
=======
Genozip is a paid professional product (:ref:`Pricing<commercial>`), provided under this :ref:`license<license>`. Genozip is also available *free of charge* for academic and training use (see :ref:`FAQ<FAQ>`).

|

.. include:: contact.rst
.. include:: publications-list.rst

.. toctree::
   :maxdepth: 3
   :hidden:

   Who is using it? <institutions>
   Installing <installing> 
   Benchmarks <benchmarks> 
   Pricing <commercial>
   Make money referring <referral>
   Publications & Citing <publications>
   Capabilities <capabilities>
   User manual <manual>
   Resellers <resellers>
   License <license>
   Testimonials <testimonials> 
   Contact <contact>
  
|

THIS SOFTWARE IS PROVIDED \"AS IS\", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE, TITLE AND NON-INFRINGEMENT. IN NO EVENT SHALL THE AUTHORS, COPYRIGHT HOLDERS OR DISTRIBUTORS OF THIS SOFTWARE BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
