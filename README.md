# vs-archive-project

Preliminary plans for the Vin Scelsa Archive Project, developed for (hopeful) future work in collaboration with [Fordham University Libraries](https://www.fordham.edu/resources/libraries/) and [WFUV](http://wfuv.org). 
- The goal of the overall project is to reformat Vin's collection of audio interview recordings and make them as accessible as copyright and storage will allow. 
- The goal of this GitHub repository is to (eventually) capture metadata and transcriptions for the interviews as well as provide status and workflow documentation.

## Repository structure for vs-archive-project
```
.
├── interviews/                         # folder per interview 
│   ├── yyyy-mm-dd-guest-name/          # template folder, showing naming format 
│   │   ├── _metadata.csv               # metadata for individual interview and digitiazed audio file
│   │   ├── _transcription_raw.md       # automatic transcription text of individual interview, generated by WhisperAI
│   │   ├── _transcription_edited.md    # edited transcription text of individual interview, reviewed by a human
├── metadata/                           
│   ├── vs-metadata-template.csv        # metadata template for the project
│   ├── compiled/                       # directory for compiled metadata for the project
│   │   ├── vs-metadata-master.csv      # compiled master metadata file
├── workflow/                           # workflow documentation
│   ├── vs-project-board.tsv            # exported data from Project Board status tracker
├── .github/workflows/                 
│   ├── create-interview-folder.yml     # Action for _metadata.csv file upload to trigger new folder creation in interviews/ directory 
├── LICENSE                             # Opted for MIT
└── README.md                           # what you're currently reading 🙂
```

## Where to start for each interview
1. From the [/metadata](https://github.com/swdrop/vs-archive-project/tree/612b461669bf237c7dab1d20db940b0a365a5e4f/metadata) directory, download the template file [vs-metadata-template.csv](https://github.com/swdrop/vs-archive-project/blob/ed7f08638c6ded2f4b809ccfba85b32ab56013a2/metadata/vs_metadata_template.csv).
2. Open template, add any known metadata for the interview and save the updated file using the interview date and guest name in the following naming format: yyyy-mm-dd-guest-name_metadata.csv.
3. Upload the _metadata.csv file to [vs-archive-project/interviews](https://github.com/swdrop/vs-archive-project/tree/33989127869e42d46d99c08327e7e5c07bbb2a41/interviews). This will trigger the Action [create-interview-folder.yml](https://github.com/swdrop/vs-archive-project/blob/705c88ea70e55f325fb3e1dc22c75f0110974b38/.github/workflows/create-interview-folder.yml) which creates a new folder for the corresponding interview, containing the _metadata.csv file.
4. Check [vs-archive-project/interviews](https://github.com/swdrop/vs-archive-project/tree/33989127869e42d46d99c08327e7e5c07bbb2a41/interviews) to confirm new folder was created, and use this folder for any future file uploads related to this interview.

## Metadata
Currently, a very basic metadata schema is in place for capturing essential identifying details of these interview recordings. Further evaluation should take place before the project progresses further to close the following Issues:
- Expand the metadata schema and align it with PBCore. To refine the fields used, refer to the [PBCore 2.1 GitHub repository](https://github.com/PBCore-AV-Metadata/PBCore_2.1.git), and remember to update any previous versions of metadata files and templates.
- Establish identification (ID) number schema and plan. The physical items need ID numbers and barcodes and each corresponding digital item should be assigned as an instantiation numbers of that main ID number.

## Project Board
[vs-archive-project-board](https://github.com/users/swdrop/projects/1/) is used as this project's central task list. Contributors to this project should add Issues and then use the Project Board to assign roles and select from the following status levels: 

- To Do
- In Progress
- Review
- Done

**@Contributors:** Please continue to update assignments and status levels as Issues are added and tasks progress.

## Credits
- Tom Waits interview information source: [Tom Waits Library.info](http://tomwaitslibrary.info/biography/interviews/wnew-fm-idiots-delight/)
- Lou Reed interview information source: [WFUV.org](https://wfuv.org/content/vin-scelsa-shares-1998-interview-lou-reed-idiots-delight)
- [ChatGPT](https://chatgpt.com/) was used to help troubleshoot errors encountered while developing the Action script for [create-interview-folder.yml](https://github.com/swdrop/vs-archive-project/blob/acf82fba800eb31864bc2f1022401d96b97a7632/.github/workflows/create-interview-folder.yml)
- Primary GitHub information (and help) source: [Chris Diaz](https://github.com/chrisdaaz)
