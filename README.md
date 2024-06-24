The first part of the theoretical questions from the document:


# Restricted Boltzmann Machine

1. Show that the sum over { ${\mathbf{h}}$ } can be carried out like

$$ e^{\sum_j a_js_j} \prod_i 2 \cosh \left( \sum_j w_{ij}s_j + b_i \right) $$

where

$$ \psi_\theta(s) \propto \sum_{\{\mathbf{h}\}} \exp \left( \sum_j a_js_j + \sum_i b_ih_i + \sum_{ij} w_{ij}h_is_j \right) $$

with

$$ h_i = \pm 1. $$

Thus,

$$ e^{\sum_j a_js_j} \sum_{\{\mathbf{h}\}} e^{ \left[ \sum_i b_ih_i + \sum_{ij} w_{ij}h_is_j \right] } $$

$$ = e^{\sum_j a_js_j} \sum_{\{\mathbf{h}\}} \prod_i e^{ h_i \left( \sum_j w_{ij}s_j + b_i \right) } $$

$$ = e^{\sum_j a_js_j} \prod_i \sum_{h_i} e^{ h_i \left( \sum_j w_{ij}s_j + b_i \right) } $$

$$ = e^{\sum_j a_js_j} \prod_i 2 \cosh \left( \sum_j w_{ij}s_j + b_i \right) $$

$$ = e^{\sum_j a_js_j} \prod_i \left[ e^{ \left( \sum_j w_{ij}s_j + b_i \right) } + e^{ -\left( \sum_j w_{ij}s_j + b_i \right) } \right] $$

$$ = e^{\sum_j a_js_j} \prod_i 2 \cosh \left( \sum_j w_{ij}s_j + b_i \right). $$

# Derivatives in Restricted Boltzmann Machine

2. (a) $O_a(s) = \nabla_a \log \psi_\theta(s)$, $O_b(s) = \nabla_b \log \psi_\theta(s)$, $O_w(s) = \nabla_w \log \psi_\theta(s)$

Explicitly calculate these derivatives.

$$ \log \left[ e^{\sum_j a_js_j} \prod_i 2 \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right] = \sum_j a_js_j + \sum_i \log \left( 2 \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right) $$

$$ = \sum_j a_js_j + 2M + \sum_i \log \left( \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right). $$

$$ O_b(s) = \nabla_b \log \psi_\theta(s) $$

$$ = \nabla_b \left[ \sum_j a_js_j + 2M + \sum_i \log \left( \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right) \right] $$

$$ = \sum_i \frac{1}{\cosh \left( \sum_j w_{ij}s_j + b_i \right)} \sinh \left( \sum_j w_{ij}s_j + b_i \right) \cdot \delta_{ik} $$

$$ = \frac{1}{\cosh \left( \sum_j w_{ij}s_j + b_i \right)} \sinh \left( \sum_j w_{ij}s_j + b_i \right) $$

$$ = \tanh \left( \sum_j w_{ij}s_j + b_i \right). $$

$$ O_b(s) = \nabla_b \log \psi_\theta(s) = \sum_i \tanh \left( \sum_j w_{ij}s_j + b_i \right) \cdot \mathbf{e}_i. $$

$$ O_a(s) = \nabla_a \log \psi_\theta(s) $$

$$ = \nabla_a \left[ \sum_j a_js_j + 2M + \sum_i \log \left( \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right) \right] $$

$$ = \sum_j s_j \mathbf{e}_j. $$

$$ O_w(s) = \nabla_w \log \psi_\theta(s) $$

$$ = \nabla_w \left[ \sum_j a_js_j + 2M + \sum_i \log \left( \cosh \left( \sum_j w_{ij}s_j + b_i \right) \right) \right] $$

$$ = \sum_i \frac{1}{\cosh \left( \sum_j w_{ij}s_j + b_i \right)} \sinh \left( \sum_j w_{ij}s_j + b_i \right) \cdot \sum_j \delta_{ik} \delta_{jl} s_j $$

$$ = \frac{1}{\cosh \left( \sum_j w_{ij}s_j + b_i \right)} \sinh \left( \sum_j w_{ij}s_j + b_i \right) \cdot s_k $$

$$ = \tanh \left( \sum_j w_{ij}s_j + b_i \right) \cdot s_k \mathbf{e}_{iN+k}. $$

2. (b) Show that $\nabla_\theta \psi_\theta(s) = O_\theta(s) \psi_\theta(s) = \nabla_\theta [ \log (\psi_\theta(s)) ] \psi_\theta(s)$

By chain rule:

$$ \nabla_\theta [ \log (\psi_\theta(s)) ] \cdot \psi_\theta(s) = \frac{1}{\psi_\theta(s)} \nabla_\theta [ \psi_\theta(s) ] \cdot \psi_\theta(s). $$

So,

$$ O_\theta(s) \psi_\theta(s) = \nabla_\theta [ \psi_\theta(s) ]. $$
