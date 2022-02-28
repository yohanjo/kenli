# Counterevidence Retrieval Dataset
This folder contains the counterevidence retrieval dataset in Section 4.2. The dataset was compiled from CMV and Kialo. 

## CMV (`cmv-annotations.jsonlist`)
- `claim_id`: Unique ID for this claim.
- `claim_text`: Text of this claim. This is a sentence from the original post.
- `post_id`: Source post ID.
- `post_sents`: All sentences of the source post.
- `post_sent_idx`: Index of the sentence the claim came from.
- `con_evidence`: Candidate counterevidence sentences included in the ground-truth dataset and evaluation.
   - `id`: Unique ID of the candidate sentence, used for annotation.
   - `ev_text`: Text of the candidate sentence.
   - `ev_context`: Context of the candidate sentence in the source document.
   - `ev_sent_idx`: Position of the candidate sentence in the source document.
   - `ev_url`: URL of the source document.
   - `ev_url_netloc`: Netloc of the source document.
   - `strength`: Annotations of counterevidence strength (0=very weak, 1=weak, 2=strong, 3=very strong).
   - `doc_needed`: Annotations of whether the annotator needed to see the source document to make a decision (0=no, 1=yes).
   - `references`: Details of the candidate sentence.
      - `claim_id`: ID of this claim.
      - `doc_cand_id`: ID of the source document this candidate sentence came from.
      - `key`: Pair of the source document URL and sentence index.
      - `nli_prob`: Probability of contradiction predicted by an NLI model.
      - `sent_rank_path`: Sentence ranking results path.


## Kialo (`kialo-annotations.jsonlist`)
It has the same format as CMV, except that `post_id`, `post_sents` and `post_sent_idx` do not exist.
