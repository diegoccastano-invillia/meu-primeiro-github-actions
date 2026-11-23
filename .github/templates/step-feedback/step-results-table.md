{% if passed %}
<img src="../images/inflatocat.png" align="right" height="100px" alt="Octocat comemorando a aprovação do passo" />

## Passo {{ step_number }} — Aprovado ✅

Ótimo trabalho! Todas as verificações passaram. Aguarde: vou preparar o próximo passo e publicar as instruções em outro comentário.

{% else %}
<img src="../images/inspectocat.png" align="right" height="100px" alt="Octocat revisando uma atividade que precisa de ajuste" />

## Passo {{ step_number }} — Precisa de um ajuste ❌

Algumas verificações ainda não passaram. Isso faz parte do exercício: confira os itens marcados e as dicas abaixo, corrija o arquivo e envie a alteração. O próximo passo será liberado quando todas as verificações passarem.

{% endif %}

| Resultado | Verificação |
| --- | --- |
{% for result in results %}| {% if result.passed %}✅ Aprovado{% else %}❌ Ajustar{% endif %} | {{ result.description }} |
{% endfor %}

{% if tips.length %}
### Dicas
{% for tip in tips %}
- {{ tip }}
{% endfor %}
{% endif %}

[Abrir a execução da avaliação]({{ run_url }})
