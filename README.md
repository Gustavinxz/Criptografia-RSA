Obs: trabalho esta no codespace
🔐 Criptografia RSA em Rust
🧩 Introdução

A criptografia RSA é um dos métodos mais importantes usados para proteger informações na internet. Ela foi criada em 1977 por três pesquisadores — Rivest, Shamir e Adleman — e é chamada de criptografia assimétrica porque usa duas chaves diferentes: uma pública e uma privada.

A ideia é simples: quando alguém quer enviar uma mensagem segura, usa a chave pública do destinatário para criptografar. Depois, só quem tem a chave privada correspondente consegue descriptografar e ler o conteúdo original.

🧮 Fundamentos Matemáticos

O funcionamento do RSA depende da matemática, principalmente dos números primos e da aritmética modular.

O algoritmo começa escolhendo dois números primos grandes, chamados p e q. Esses dois números são multiplicados para formar n, que será usado em todas as operações. Depois, é calculado o valor φ(n) (função totiente de Euler), que indica quantos números menores que n são coprimos com ele.

Em seguida, é escolhido um número e, que precisa ser coprimo com φ(n). Por fim, calcula-se o inverso modular de e, chamado d.
Com isso, temos:

Chave pública: (n, e)

Chave privada: (n, d)

⚙️ Funcionamento do Algoritmo

Quando alguém quer criptografar uma mensagem, o texto é transformado em número e o cálculo feito é:

c = m^e mod n

m é a mensagem original;

c é o texto criptografado.

Para descriptografar, o dono da chave privada faz o processo inverso:

m = c^d mod n

Graças às propriedades matemáticas do RSA, o resultado final é exatamente a mensagem original.

🔒 Segurança do RSA

A segurança do RSA vem da dificuldade de fatorar números grandes. Quando n é o produto de dois primos enormes, descobrir quais são esses primos é praticamente impossível com os computadores atuais.

Por isso, o RSA é considerado um dos métodos mais seguros e é amplamente usado em:

Sites com HTTPS (aquele cadeado do navegador);

Assinaturas digitais;

Troca de chaves seguras em conexões como SSH.

⚡ Limitações

Mesmo sendo muito útil, o RSA tem alguns pontos fracos:

É mais lento que outros tipos de criptografia;

Não é indicado para criptografar arquivos grandes;

Pode ser quebrado por computadores quânticos no futuro.

Por isso, ele é usado junto com outros algoritmos, como o AES, em sistemas híbridos que juntam segurança e velocidade.

🧠 Conclusão

O RSA é um ótimo exemplo de como a matemática pode proteger dados e comunicações. Ele mostra que números primos e operações modulares podem garantir segurança real no mundo digital.

Neste projeto, o objetivo foi implementar o RSA em Rust, entendendo como gerar as chaves, criptografar e descriptografar mensagens, e observar como a teoria matemática se transforma em prática dentro da programação.
