# Appendix: Formal Contracts and Worked Records {#sec:appendix}

Let a retained document consist of physical PDF pages $P = (p_1,\ldots,p_n)$. For the selected extractor, let $t_i$ be the exact UTF-8 text assigned to page $i$, and let $L_i$ count its nonempty extracted lines. The reported denominators are

$$
N_{\mathrm{pages}} = n, \qquad N_{\mathrm{lines}} = \sum_{i=1}^{n} L_i.
$$

The profile reports the minimum, median and maximum of the complete sequence $(L_1,\ldots,L_n)$, including zeros. These are extraction statistics. They do not define a legal segmentation or a probability sample. Changing page layout, fonts or extractor behavior can change the line-count distribution without changing the substantive law.

Replay acceptance requires the configured source identity, original PDF hash, physical page membership and exact extracted texts to agree with the retained receipt. Publication correspondence additionally requires the selected Git reference to contain the same public input and native packet bytes. Neither relation implies semantic truth or continuing legal currency.

![Recorded source structure, selected operating policy and native rendering support separate claims. Human review and legal currency are outside these mechanical checks.](../output/figures/evidence-boundaries.png){#fig:evidence-boundaries}

The claim ledger records the scope and unestablished outcomes alongside each evidence locator. This is a practical traceability device rather than a formal proof of correctness. It makes disagreements locatable: an extraction mismatch, a source-identity change and a substantive legal objection should not be collapsed into one undifferentiated build result.
