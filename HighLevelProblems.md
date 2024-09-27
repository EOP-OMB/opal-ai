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
- [X] How to convert SP 800-53 controls into a format from which we can automatically generate assessment prompts
  - Approach: Use pandas to pull out controls directly from xlsx version
- [X] How to capture project documents into a RAG database for section retrieval for assessment
  - Approach: Use gpt-4o to identify sections, embed the sections using OpenAI, and store them using vectordb (or Pinecone)
- [X] How to generate keywords from SP 800-53 controls to extract corresponding sections from the RAG database for assessment
  - Approach: Use an embedding of the control itself as the search term
- [X] Given a control how do we generate prompts or a prompt workflow to:
  - Gather evidence for a control (document, section, actual text)
  - Identify values for the control variables
  - Approach: Use a CrewAI workflow that:
    - Searches documents using RAG
    - Uses one step to pull out evidence from the found document segments
    - Populates parameters from the control from the evidence
    - Evaluates if the control is met based upon the evidence
    - Formats the evaluation result into an XML document
- [ ] Given control evidence and values, how do we put it in a format that is either in OSCAL or can be converted into OSCAL in the future
  - Partial Approach: Use a step in the CrewAI workflow to format evidence into an XML document matching a specific schema
- [ ] How do we iterate over all of the controls and package the results into a full assessment

## Future Work
- Currently the workflow "hallucinates" parameters when none is in the control.
  - Can we set up workflow steps to clearly identify the parameters (if any) and conduct QA on the workflow output?
- Use an OSCAL-compatible format for individual results
- Come the results from multiple evaluations into an OSCAL-compatible format
- Improve the LLM prompt that identifies sections within a document
- Gracefully handle documents that are too large for a single LLM call
- Support local LLM models (such as ollama)
- Convert the notebooks into a stand-alone Python library