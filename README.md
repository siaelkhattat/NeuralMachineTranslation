# NeuralMachineTranslation
NMT models rarely learn phrase- and syntax-level alignments explicitly, unlike SMT. We inject this missing structural knowledge into an NMT model through a constituent-alignment discriminator that guides its fine-tuning, for Darija→English, a low-resource setting with no treebank

Method A and Method B
Method A (baseline)
Model : Marian fine-tuned Darija->English
Loss : Cross-entropy only (predict each next word)
Variants : A0: no fine-tuning. A1: fine-tuned.
           A2: fine-tuned for extra steps

Method B (guided)
The same model, plus a constituent-alignment discriminator D
loss : Cross-entropy + 1:L_G, where D scores the whole translation's constituent alignment
variants : BO: D reranks the 8-best list (no extra training). 
           B1: D at sentence level. B2: D at constituent level

           
Method B gets extra fine-tuning steps, so A2 gives Method A the same extra steps. Without it, any gain could simply come from training longer.




