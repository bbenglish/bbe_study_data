👋 Hi, I’m Toma. Well met! This repository hosts de-identified data from research conducted at https://bestbanana.cc. My work focuses on English education, with a particular interest in Extensive Viewing and its application in Computer-Assisted Language Learning (CALL). I am currently researching how Extensive Viewing can support language learning in distance education environments. I welcome collaboration with educators, researchers, and practitioners who share an interest in language education and educational technology. 📫 Feel free to contact me at [english@bestbanana.cc](mailto:bestbanana.tw@gmail.com).

# Interview Data

At the end of our class, Helloworld in English, we ask students to leave a comment by answering this question: "What do you think of our class?" Click here to see all responses collected from 2021 to 2026: [Student Feedback](https://docs.google.com/spreadsheets/d/1eaEXQXGbZ-rUnPOWOEZAvUQNntKqXzvfYMro2VMk0vo/edit?usp=sharing)

The video summarizes a total of 1,023 responses collected during the first five semesters and analyzed using NotebookLM: https://youtu.be/LAib29tcMcQ or [BBE subtitled version](https://english.bestbanana.cc/cinema?v=LAib29tcMcQ).


# Survey Data

1101_pre.xlsx differs from 1101.xlsx, in that some participants didn't do the post-survey, yet their opinions are still valid. You can see it in Sheet1 of the data. 

1102.xlsx & 1102_pre.xlsx are designed for the use of other research. However the question regarding the evaluation of English utilization frequency is of value and thus included here. Experiment 1101 took place six months prior to Experiment 1102, each lasting four months.

Meta data is located on the second sheet of each excel.

The column "Intervened" is 1 if the score of the semester is no less than 70, which is considered as exposed enough to the course intervention--otherwise it is 0.

Pre_liner column evaluation starts from the column named \_pre\_hbt\_1 to \_pre\_tbb\_1
since it is the beginning of the body of the questionnaire, where people are most likely to give linear responses. In a similar way the pst_liner column was elicited.

Note that in meta sheet, the pre_trapped as well as pst_trapped question description is hidden among the question columns. We didn't move it to the front to align it with the original questionnaire.

In the meta data sheet, the column "Participant" is the number of all course students who we invited to fill out the survey; The column "Response" represents the count of responses we received; The column "Rate" is simply the quotient of the participants over the responses; The column "Respond_twice" shows the number of people who did both the pre- & post-survey.

In the meta data sheet, the column "Participant" is the number of all the course students who we invited to fill out the survey; The column "Response" represents the count of responses we received; The column "Rate" is simply the quotient of the participants over the responses; The column "Respond_twice" shows the number of people who did both the pre- and post-survey.

# Monitoring Design

When learners start watch videos on the course platform (bestbanana.cc), the date as well as how much time spent watching is recorded. This provides useful information gauging the treatment-receiving situation across the whole sample. However, fake exposure to the treatment can be very serious when it comes to education. It is very common to see students in a classroom without paying attention to the learning materials, let along in a distance education environment. To avoid fake exposure to the treatment, we design some monitoring functions as follows:
* Counting on playing. Only when the video is playing, does the stopwatch system starts counting.
* Staying on the page. Once a learner leaves the video page, the video stops playing and thus the stopwatch stops as well.
*	Interaction detector. If a learner doesn’t interact with the video at all, e.g., clicking on the subtitle for dictionary function, clicking the sentence jumping button, etc., a confirming dialog pops out to make sure one does not leave a video playing without watching it.
*	True English video detector. This function ensures the video loaded into the course platform is actually pronounced in English.

The complicate mechanism of the confirming dialog is as follows: The time one doesn’t interact with the platform at all is recorded as Inactive Time (IT). IT reset to zero once the learner clicks anywhere on the screen or presses any hotkey button on the keyboard. A confirmation dialog pops out once the cheating detector finds the IT exceeds some limits. The participants are required to confirm they are still watching within 20 seconds, or otherwise the time gathered for their assignment would be subtracted as a punishment. The IT limits are set as follows: (a) 4~6 minutes for the first IT limit, (b) 4 minutes times 2 to the power of the confirmed number of times afterwards, and (c) 12 seconds prior to the end of the video if the limit exceeds the total video duration. Note that the first limit of time is randomly assigned in case one would use a timer to cheat. Besides, the subsequent limits increase quadratically because we don’t want to ruin the watching experience too much. For example, one could reach the first limit at 4 minutes and after confirming, if there is still no interaction, he or she is going to meet another time limit as 4 * 2^1, that is 8 minutes later. The third time limit would be 4 * 2^2, that is 16 minutes after the second pop-up dialog was confirmed, and so on and so forth. If failing to answer the third confirmation dialog, the learner loses 16 minutes on the daily viewing time record then. The minimum time record is zero for that day.

In addition to fake watching, some videos have English subtitles except that the language spoken is not English, and some videos spoken in English are subtitled in Chinese. We try to prevent students from taking advantage of these for assignments via the detection of non-English characters in videos’ titles as well as the channel names. The rule is to have no more than 80% non-English characters in the video title as well as the channel name. Zero tolerance is not the case because some videos use “emoji,” such as facial expression characters. Videos like this one are not acceptable: https://www.youtube.com/watch?v=diCgX_KnRdU (Chinese subtitles with English dub).
