# Kidney and Kidney Tumor Segmentation for CT images
## Background
### Segmentation task
Kidney tumors are notorious for their conspicuous appearance in computed tomography (CT) imaging, and this has enabled important work by radiologists and surgeons to study the relationship between tumor size, shape, and appearance and its prospects for treatment. It’s laborious work, however, and it relies on assessments that are often subjective and imprecise.
Automatic segmentation of kidney and kidney tumors is a promising tool for addressing these limitations: Segmentation-based assessments are objective and necessarily well-defined, and automation eliminates all effort save for the click of a button.
### Prediction task
Up to 30% of renal masses ≤4cm are found to be benign at the time of surgical excision, raising concern for overtreatment. However, the risk of malignancy is currently unable to be accurately predicted prior to surgery using imaging alone. Although renal mass biopsy has a relatively low complication rate, it is an invasive procedure and has a non-diagnostic rate of up to 22%. Therefore, another task is to develop a non-invasive and accurate method for pre-operative renal tumor classification using readily available clinical and CT imaging data.

## The data
This patient cohort includes patients who underwent kidney nephrectomy for suspected renal malignancy at the UF Health Shands Hospital. The CT images before the kidney nephrectomy of these patients were extracted from UF Health IDR.
For each CT image, we need to obtain the segmentation of the kidney and kidney tumor for the downstream prediction task. We will adopt a two-step approach for the segmentation:
1. Apply automatic segmentation models on the raw data to generate the segmentation for kidney and kidney tumor.
2. A manual segmentation team will examine the accuracy of the automatic segmentation and manually improve the segementation if needed.

## Segmentation improvement process
### Task management
We use Github Project (https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects) to manage the whole segmentation improvement process. Every participant will need to register a Github account and then be added into the project.

![Segmentation Improvement Task Management](https://github.com/YeechingTiger/Renal-Cancer-CT-Segmentation/blob/main/task_management.png?raw=true)
**Figure 1**. The screenshot of the task management user interface

We placed members of our team into three categories:
  * **Experts**: Attending radiologists and urologic cancer surgeons
  * **Trainees**: College of Medicine students. All trainees received several hours of training from the experts and recorded Youtube tutorials
 * **Coordinators**: Team members who create, assign and monitor the  tasks

Each task has several Status (shown in **Figure 1**):
  * **Todo**: The task has been created but not started
  * **In Expert Annotation Progress**: The expert is examining the CT segmentation results and adding improvement guidelines
  * **In Trainee Annotation Progress**: The trainee is modifying the CT segmentation according to expert's guidelines
  * **In Expert Review**: The expert is reviewing the modified segmentation
  * **Done**: This segmentation is approved by the expert

### Annotation process
Broadly, our annotation process is as follows.
1. The **Coordinators** will create the task, add neccessary information (e.g., CT file location), and assign an expert and a trainee for the task (**Figure 1** and **Figure 2**). For each task, there is a specific channel (i.e., Github Issues) in which the coordinator, expert and trainee could discuss the annotation.
![Task information](https://github.com/YeechingTiger/Renal-Cancer-CT-Segmentation/blob/main/task_information.png?raw=true)
**Figure 2**. Neccessary information for a task

2. The **Expert** will get a notification of an assigned task, and begin to examine the automatic segmentation result. A web-based segmentation tool call MedSeg will be used to examine and modify the existing segmention. The **Expert** will complete the following steps:
    * If specific segmentation is too large or small, circle the kidney or tumor and add "-" or "+" symbols to indicate the improvement needed. (**Figure 3**)
    ![part](https://github.com/YeechingTiger/Renal-Cancer-CT-Segmentation/blob/main/partial_issues.png?raw=true)
    **Figure 3**. Partial segmentation issue
    * If a segmentation for kidney or tumor is missing, circle it and add "+++" symbol to indicate "annotate this part". (**Figure 4**)
    * If a segmentation is totally wrong and need to be removed, use "---" symbol. (**Figure 4**)
    ![part](https://github.com/YeechingTiger/Renal-Cancer-CT-Segmentation/blob/main/total_issues.png?raw=true)
    **Figure 4**. Missing or wrong segmentation issues

    Meanwhile, the expert could add any comments in the task channel to guide the trainee to modify the current segmentation. Note that the CT images are in 3D format, thus there could be a series of problematic CT slides for one segmentation issue, and the expert could only annotate several slides and the trainee need to figure out other slides.
    When the improve guidelines are finished (for both image annotation and task channel comments), the expert need to download the current segmentation files and then upload to a shared Dropbox for this task, and then change the task status to **In Trainee Annotation Progress**.

3. The **Trainee** should get a notification to indicate he/she could start the segmentation improvement. According to the expert guidelines, the trainee will use the MedSeg tool to modify the segmention, remove expert's guideline and download the final clean segmentation result. Then, the segmentation result file need to be uploaded to the shared Dropbox, too. Then, the status of the task should be change to **In Expert Review**.

4. The **Expert** should get a notification which indicates that the task need to be reviewed. If any issue identified, the expert will create the new guideline, and notify the trainee to modify the segmentation. If the current segmention is approved, the expert will change the task status to **Done**.

## Annotation Tool - MedSeg
* Home page: https://www.medseg.ai/
* Youtube tutorial from MedSeg: https://www.youtube.com/channel/UCSexzngll7DQoVo923iBjNA
* Youtube tutorial for this project: **TBD, will need a student of Dr. Jie Xu to do that. Xing could give some help.**
