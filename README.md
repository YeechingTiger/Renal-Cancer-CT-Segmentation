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
2. An manual segmentation team will examine the accuracy of the automatic segmentation and manually improve the segementation if needed.

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
1. The **Coordinators** will create the task, add neccessary information (e.g., CT file location), and assign an expert and a trainee for the task (**Figure 1** and **Figure 2**)
2. 
