# NIST SP 800-53 rev 5 Control Documentation
This folder contains the NIST SP 800-53 rev 5 controls in:
 * PDF format (from https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final ), 
 * OSCAL JSON format (from https://github.com/usnistgov/oscal-content/tree/main/nist.gov/SP800-53/rev5/json ), and
 * OSCAL XML format (from https://github.com/usnistgov/oscal-content/tree/main/nist.gov/SP800-53/rev5/xml ).

Our challenge will be to iterate through each control and convert it into:
 1. A series of effective keywords and phrases to locate evidence in a document repository (RAG database)
 2. A series to effective exmaniation questions to:
    a. Determine the satisfaction of the control from the evidence
    b. Identify properties (variables) in the control from the evidence
