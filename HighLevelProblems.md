# Review of the High Level Problems
## Key References
 - SP 800-53 controls: <https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final>
   - OSCAL Format: <https://github.com/usnistgov/oscal-content/tree/main/nist.gov/SP800-53>
 - OSCAL Resources:
   - Concepts and overview: <https://pages.nist.gov/OSCAL/resources/concepts/layer/overview/>
   - Control example: <https://pages.nist.gov/OSCAL/resources/concepts/layer/control/catalog/sp800-53rev5-example/>
 - Examples we can use to search:
   - EPA security policy and procedures: <https://www.epa.gov/irmpoli8/information-security-policy-procedures-and-standards>
   - AWS is a second option

## Sub-problems
- [ ] How to convert SP 800-53 controls into a format from which we can automatically generate assessment prompts
- [ ] How to capture project documents into a RAG database for section retrieval for assessment
- [ ] How to generate keywords from SP 800-53 controls to extract corresponding sections from the RAG database for assessment
- [ ] Given a control how do we generate prompts or a prompt workflow to:
  - Gather evidence for a control (document, section, actual text)
  - Identify values for the control variables 
- [ ] Given control evidence and values, how do we put it in a format that is either in OSCAL or can be converted into OSCAL in the future
- [ ] How do we iterate over all of the controls and package the results into a full assessment

## Prioritzation of the problems
The idea is to start small and focus on high-risk elements.

 1. Given a control description and text, design prompts to
    - Gather evidence (document, section, actual text)
    - Identify values for control variables
 2. Figure out how to get the control description and text automatically from OSCAL or the PDF
    - *Milestone:* At this point we should be able to evaluate any control automatically against a specific piece of text
 3. Figure out how to split and import the software policy documentation into a RAG database
 4. Figure out how to use the control to search the RAG database and extract software policy sections
    - *Milestone:* At this point we should be able to evaluate any control automatically against a whole libray of policies
 5. Figure out how to format the control results into OSCAL-translatable json (not necessarily a full OSCAL format)
 6. Figure out how to loop through all of the controls (or a specified subset) and combine the results
    - *Milestone:* At this point we should be able to store policy documents and then automatically evaluate the policy against all controls, resulting in a machine readable format
