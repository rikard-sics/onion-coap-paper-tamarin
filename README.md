# Tamaring Prover model for the paper Onion CoAP: Enabling Onion Routing for the IoT

The two files above contains the Tamarin Prover model for the Onion CoAP protocol single-circuit version, and the Tamarin proofs that the specified properties are valid.

Both files contain the same model, but the proofs for different lemmas. We split the proofs over two different .spthy files due to their large size (over 30,000 lines in total), and correspondingly large memory footprint to verify.

Please note that the notations between this Tamarin model and the paper is not 100% consistent, as our notations evolved to improve clarity and readability in the paper, but we did not update the notations in the .spthy file accordingly. The reader should be able to make the correspondance.

To verify a file, simply start tamarin in a directory containing those files then load it by clicking on the corresponding line in Tamarin GUI. When Tamarin loads a file, it automatically verifies and validate the proofs contained within.
"tamarin-prover interactive ."


* 0_OnionCoAP_source_lemma.spthy
This file contains the proof trace for the source lemma, an auxiliary re-usable lemma that is automatically used by Tamarin to refine the sources for the main lemma.
 - Verification:
   * time: ~5 min (2021 Lenovo laptop)
   * memory: ~17 GB
   
* 1_OnionCoAP_all_but_sources.spthy
This file contains the proof traces for all other lemmas relevant to the paper beside the source. Most of them are support lemmas marked as reuse, and the two key lemmas supporting the claims in the paper are: 
 - executable_S, which shows that the protocol work as intended.
 - weak_no_linkage, which shows that Proxies cannot learn both end-points of a circuit. The "weak" in the lemma's name refers to the formulation of the property, which is easier to prove under this form, but is equivalent to the natural language phrasing, as we explain in the paper section 11.2.  
 - Verification:
   * time: ~5 min (2021 Lenovo laptop)
   * memory: ~10 GB

Model Author: Simon Bouget

Paper Authors: Rikard Höglund, Marco Tiloca, Christian Amsüss, Simon Bouget, Shahid Raza
