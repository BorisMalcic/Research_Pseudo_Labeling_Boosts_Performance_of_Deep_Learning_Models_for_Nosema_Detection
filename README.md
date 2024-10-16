# Paper: Pseudo Labeling Boosts Performance of Deep Learning Models for Nosema Detection on Microscopic Images 

    #Authors: 1. M.Sc. Boris Malcic, Faculty of Electrical Engineering, University of Banja Luka, Republic of Srpska (RS), Bosnia and  Herzegovina (BiH). Corresponding author's e-mail address: boris.malcic@etf.unibl.org
    #         2. Dr. Violeta Santrac, PI Veterinary Institute of the Repubic of Srpska "Dr. Vaso Butozan", 78000 Banja Luka, RS, BiH
          
# This is description for a data (programs, datasets, trained models and validation results) you need to check and/or repeat research presented in the paper.

## Steps:

#1. You can use our dataset (in YOLOv8 folder) or prepare your own dataset (microscopic images and annotation files in normalized YOLO format using software tool e.g. [LabelImg](https://github.com/tzutalin/labelImg). First, extract boris_github.rar on your local machine. 
# 1.1 NOTE: Example of our initial dataset (originally recorded microscopic images and labels) are in folder path: boris_github\YOLOv8\prof_risojevic\arhiva\slike_nosema\originalne_mikroskopske_slike_u_2_puta_vecoj_rezoluciji\all_original_microscopic_images_and_their_annotations
#2. We have been training detectors (YOLOv8x models for Nosema detection) on three computers and you can find three folders (in the folder boris_github) where are data (some of trained models, test results, etc.) on each of the computers (in the following text the folders are abbreviated as name_of_computer): 1. infiltrator_computer, 2. phoenix_first_computer, and 3. phoenix_middle_computer. Furthermore, there is also 4th folder (in the folder boris_github) with name YOLOv8 where are datasets (original microscopic images and random splits of original microspopic subimages and their annotation files that have been used in the training). The folder YOLOv8 needs to be copied in each folder on path: name_of_computer/Phoenix/YOLOv8 if you want to repeat training on each of the computers. That needs to be fullfiled if you want to use our programs, or if you read a comments in the programs - you can easily modify paths in our programs for your needs.

#3. In each of the previous three folders there is folder Phoenix that we had on Desktop of each corresponing computer with CUDA support for training (for more details read the paper).
#4. In Phoenix folder (for each computer) is located boris_phoenixbee_environment.yml file that you need to recreate Anaconda environment that we have used.
#(For more information on how to create Anaconda environment using .yml file, please visit: https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)

#5. Our subblock images and their annotation .txt files are stored in validation, test and training subfolders(for every random split with subfolders' sufixes: seed_1, seed_2, ..., seed_10 ) in folder path: name_of_computer\Phoenix\YOLOv8\prof_risojevic\arhiva\slike_nosema\originalne_mikroskopske_slike_u_2_puta_vecoj_rezoluciji\subfolders

#(NOTE: You need to copy boris_github\YOLOv8 folder into path: name_of_computer\Phoenix\  or you must change folder paths in the programs with your file locations)

#6. Moreover, in subfolder named U_set (i.e. U - Unlabeled) are 16 original microscopic .bmp images (3664x2748 pixels) used for pseudolabeling
#Furthermore, in subfolder named test_set (e.g. in folder path: boris_github\phoenix_middle_computer\Phoenix\YOLOv8\prof_risojevic\arhiva\slike_nosema\originalne_mikroskopske_slike_u_2_puta_vecoj_rezoluciji\test_set if name_of_computer is phoenix_middle_computer) are 3 originally recorder .bmp microscopic RGB images in 3664x2749 pixel resolution.

#7. a) Next, there are 7 original RGB microscopic images (convertet from .bmp into .jpg format) saved in subfolder path: boris_github\phoenix_middle_computer\Phoenix\YOLOv8\prof_risojevic\arhiva\slike_nosema\originalne_mikroskopske_slike_u_2_puta_vecoj_rezoluciji\samo_tp_slike_3664x2748. 

#NOTE: These images are used for training set (in our case the 100% of L set is 5 of these 7 images, and validation set makes remaining 2 images). All programs used in our research are in folders at paths: name_of_computer\Phoenix\YOLOv3-Custom-Object-Detection-main\ 

#b) To create the previous subfolder (in Serbian language the subfolder name is samo_tp_slike_3664x2748, or if you run the translated English versions of programs the corresponding subfolder name will be only_tp_images_3664x2748 in English), we run cells from our original (written in Serbian/Boasnian/Croatina latin fonts) Python Jupyter Notebook scrip entitled Program_koji_uzima_samo_tp_0_objekte_u_anotacione_fajlove.ipynb which English translated version is: english_translated_Program_that_takes_only_tp_0_objects_into_annotation_files.ipynb 

#c) Lookout, if you execute English translated version of the program, than you will create folder named "only_tp_images_36664x2748" instead of corresponding original folder in Serbian language named "samo_tp_slike_36664x2748". NOTE - The similar applies for each of translated programs!!!

#d) After that, to create random dataset split and corresponding annotation files for training (L_set) and validation, we run cells from original Serbian/Bosnian/Croatioan program entitled korektno_pravljenje_podslika_anotacija_podfoldera.ipynb that is translated into English version named:
#english_translated_correct_creating_subimages_annotations_subfolders.ipynb 

#e) After that, if you want to train your models, you would need to download and store yolov8.pt (or yolov10.pt if you want to use YOLOv10) model in paths boris_github/computer_name/Phoenix/YOLOv3-Custom-Object-Detection-main  and execute lines from our original program named modifikovani_my_last_YOLOv8_training.ipynb (the English translated program version is: english_translated_modified_my_last_YOLOv8_training.ipynb). In that program, please read carefully all comments and you shouldn't have any problems to repeat our results presented in the paper.

#f) Note: 
#	During this project, we wrote the original programs in Serbian (Cratian, Bosnian) language and run those programs. The outputs of all programs are in Serbian language, but to be available for everyone we translated all programs into English. We did not run the English translated versions of programs, because that need much time. But, if you run the translated versions of programs your dataset files will also be translated into English language and you need to be carefull about the file paths and chech everything - please read comments in the translated programs
#If you want to recreate dataset files you need to run and read comments in the following order of programs: 1st. Open Anaconda environmet in terminal, 
#  2nd. run command jupyter notebook in the Anaconda terminal, 
#  3rd. after running jupyter notebook command in the Anaconda terminal it should open in your default web browser path with programs e.g. http://localhost:8888/tree/Desktop/Phoenix/YOLOv3-Custom-Object-Detection-main/newest_programs, 
#  4th. Run (also, read comments and/or make changes for your path folders) every cell of the original Serbian/Bosnian/Croatian version of program named Program_koji_uzima_samo_tp_0_objekte_u_anotacione_fajlove.ipynb or its translated English program version english_translated_Program_that_takes_only_tp_0_objects_into_annotation_files.ipynb,
#  5th. Run (please read comments and/or make changes for your paths) every cell of the original Serbian/Bosnian/Croatian version of the program named korektno_pravljenje_podslika_anotacija_podfoldera.ipynb or its translated English program version named english_translated_correct_creating_subimages_annotations_subfolders.ipynb
#  6th. Run (please read comments and/or make changes for your file paths) every cell of the original Serbian/Bosnian/Croatian language version of the program named modifikovani_my_last_YOLOv8_training.ipynb or its translated English program version named english_translated_modified_my_last_YOLOv8_training.ipynb ,
#  7th. For verification of trained detectors (validation and testing results of mAP50 in the paper) run the cell Ln[2] before the last cell in Serbian/Bosnian/Croatian version of the program named for_testing_from_infiltrator_modifikovani_my_last_YOLOv8_training.ipynb or its translated English version named english_translated_for_testing_from_infiltrator_modified_my_last_YOLOv8_training.ipynb .
#  8th. The last program can be used for calculating (summing) total number of objests (Nosema spores) in annotation .txt file for every microscopic images.

#8. The 26 original microscopic images (used for training, test, validation and U_set) were chosen as "well recorder images" from all recorder microscopic images and their annotation files that are located in folder path: D:\boris\phoenix_first_computer_\Phoenix\YOLOv8\prof_risojevic\arhiva\slike_nosema\originalne_mikroskopske_slike_u_2_puta_vecoj_rezoluciji\sve_prvobitne_originalne_mikroskopske_slike_i_anotacije

#NOTE: Names of folders, subfolders and original Python programs are written in Serbian/Bosnian/Croatian latin language. 

#########################################################################################################################
#9. All programs are in folder path: boris_github\newest_programs. The programs need to be copied into path name_of_computer\Phoenix\YOLOv3-Custom-Object-Detection-main\ for each computer.

#In those folders you can find original programs (.ipynb) with their outputs written in Serbian/Bosnian/Croatian language. Also, for each program there is English translated program version entitled as english_translated_then_name_of_original_program_translated_into_english.ipynb file. 

#10. Some of the trained detectors are in folders' directories at paths: name_of_computer\Phoenix\YOLOv3-Custom-Object-Detection-main\runs . If you run programs by your own, here will be all trained detectors. However, we only uplaod few of the detectors because of the memory limitation for github account.

#Moreover, as an example the training results (P_curve, R_curve, mAP50, mAP50-95 curves etc.) with subfolder weights (after 30 epoch of the training there will be memorized the best trained model during epochs named best.pt and the last trained model named last.pt) for one of the trained models is on folder path: D:\boris\phoenix_first_computer_\Phoenix\YOLOv3-Custom-Object-Detection-main\runs\detect\corrected_conf_050_using_80_percent_background_yolov8x_40_posto_L_skup_training_with_clean_pseudolabels_seed_1

#####################################################################################################################################
