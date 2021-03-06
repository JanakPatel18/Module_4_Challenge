# Module_4_Challenge


## The Overview of the School District Analysis

	The purpose of the analysis was to see if there was academic dishonesty by Thomas High School (THS) and how it affected the overall results of all the schools.  The whole school wasn’t suspected of academic dishonesty, just the ninth grade.  Code was written to take THS’s ninth graders’ scores out and calculate the rest of the data and produce results.

## Results

After looking at the results, it was shown that the average math score was higher with the ninth graders but the percentage was lower.  The reading score and percentage, on the other hand were both higher without the ninth graders’ scores.  These numbers were for the district.  The school results were affected by the ninth graders’ scores.  The average score is higher both categories.  The percentage on the other hand, remains the same for math, but is higher with the ninth graders’ scores in the results.

This was used to factor out the ninth graders’ scores:

	student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"),"reading_score"] = np.nan

	student_data_df

This was used to factor out the ninth graders’ math scores:

	student_data_df.loc[(student_data_df["school_name"] == "Thomas High School") & (student_data_df["grade"] == "9th"),"math_score"] = np.nan

	student_data_df
	
This was used to get the district summary:

Create a DataFrame

district_summary_df = pd.DataFrame(
          [{"Total Schools": school_count, 
          "Total Students": student_count, 
          "Total Budget": total_budget,
          "Average Math Score": average_math_score, 
          "Average Reading Score": average_reading_score,
          "% Passing Math": passing_math_percentage,
         "% Passing Reading": passing_reading_percentage,
        "% Overall Passing": overall_passing_percentage}])



Format the "Total Students" to have the comma for a thousands separator.

district_summary_df["Total Students"] = district_summary_df["Total Students"].map("{:,}".format)
Format the "Total Budget" to have the comma for a thousands separator, a decimal separator and a "$".
district_summary_df["Total Budget"] = district_summary_df["Total Budget"].map("${:,.2f}".format)
Format the columns.
district_summary_df["Average Math Score"] = district_summary_df["Average Math Score"].map("{:.1f}".format)
district_summary_df["Average Reading Score"] = district_summary_df["Average Reading Score"].map("{:.1f}".format)
district_summary_df["% Passing Math"] = district_summary_df["% Passing Math"].map("{:.1f}".format)
district_summary_df["% Passing Reading"] = district_summary_df["% Passing Reading"].map("{:.1f}".format)
district_summary_df["% Overall Passing"] = district_summary_df["% Overall Passing"].map("{:.1f}".format)

Display the data frame

district_summary_df



## Summary

	After analyzing the data, it was shown that by removing the math and reading scores of the ninth graders’ scores, there were some areas that had a positive affect and other areas where there was a negative effect.  The math and reading scores were affected in a positive way where both the average and the percentage went up across all the school.  On the other hand, the numbers within the school were only affected in the reading scores, where the average was higher without the ninth graders’ scores, but the percentage was higher with the ninth graders’ scores.
