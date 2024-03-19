# Dashboard Home Assistant

Esse exemplo de Dashboard foi adaptado originalmente do repositório de Mattias - https://github.com/matt8707/hass-config/tree/master - o qual agradeço por compartilhar.
Resolvi traduzir algumas coisas para o Português e adaptar para minha realidade.

# Instalação

- Instalar e configuar o [HACS](https://hacs.xyz/)
  
- Instalar os componentes no Frontend pelo HACS:
  - [button-card](https://github.com/custom-cards/button-card)
  - [card-mod](https://github.com/thomasloven/lovelace-card-mod)
  - [layout-card](https://github.com/thomasloven/lovelace-layout-card)
  - [Swipe Card](https://github.com/bramkragten/swipe-card)
  - [browser-mod](https://github.com/thomasloven/hass-browser_mod)

- Copie manualmente esse arquivos abaixo de <a href="https://github.com/valsesia/dashboardHA">valsesia/dashboardHA</a>

  - ui-lovelace.yaml
  - button_card_templates (pasta)
  - popup (pasta)
  - themes (pasta)
  - sidebar.yaml

- No configuration.yaml, adicione as seguintes linhas:

```yaml
frontend:
  extra_module_url:
    - /hacsfiles/lovelace-card-mod/card-mod.js
  themes: !include_dir_merge_named themes

template: !include sidebar.yaml

lovelace:
  mode: yaml
  resources:
    - url: /hacsfiles/button-card/button-card.js
      type: module
    - url: /hacsfiles/lovelace-layout-card/layout-card.js
      type: module
    - url: /hacsfiles/swipe-card/swipe-card.js
      type: module
```
- [Reiniciar](https://my.home-assistant.io/redirect/server_controls/) o Home Assistant
- Selecionar o modo escuro e o [tema tablet](https://my.home-assistant.io/redirect/profile/) (dentro da pasta THEME) <- NÃO PULE ESSA ETAPA
- 
