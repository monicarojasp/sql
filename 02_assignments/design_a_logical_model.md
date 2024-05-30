# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

![image](https://github.com/monicarojasp/sql/assets/105380675/ead7ece8-b359-4014-862f-28338d419c46)


## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

![image](https://github.com/monicarojasp/sql/assets/105380675/4204dd26-546c-490c-b7c4-cbbc15b88b3b)


## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Type 1 SCD In this architecture, the customer_address table overwrites changes by updating existing records with new address information.

customer_address table
customer_id	address	   city	   province	   postal_code
      1	   address	   city	   province    postal_code
      2   	address	   city	   province	   postal_code
      3   	address	   city	   province	   postal_code
      4   	address   	city	   province	   postal_code


Type 2 SCD In this architecture, the customer_address table retain existing records with new address information and keeps a history of the changes

Customer_address table
customer_key	customer_id	address	   city	   province	   postal_code	   start_date	   end_date
      1	            1	   address_1	city_1	province_1	postal_code_1	 2012-07-02	   2016-02-11
      2	            1	   address_2	city_2	province_2	postal_code_2	 2016-02-12	   NULL
      3	            2	   address_1	city_1	province_1	postal_code_1	 2020-05-03	   2023-08-01
      4      	      2   	address_2	city_2	province_2	postal_code_2	 2023-08-02	   NULL


```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
By comparing my Entity-Relationship Diagram (ERD) with the AdventureWorks 2008 schema, I noticed a couple of differences. Firstly, the AdventureWorks schema includes product vendor information, which is not present in my ERD. To enhance the applicability of my ERD, I would incorporate a supplier/vendor table. This addition would allow the bookstore to track where it sources its books from and manage incoming shipments effectively.

Additionally, the AdventureWorks schema features a Product Review table, which I find intriguing and beneficial for my ERD. By including a ProductReview table, my ERD can capture valuable customer feedback on specific books. This information can aid in decision-making processes regarding book selection and inventory management.

```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
