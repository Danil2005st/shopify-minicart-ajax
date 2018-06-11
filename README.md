# shopify-minicart-ajax


прописываем подключения

  <!--[if (gt IE 9)|!(IE)]><!--><script src="{{ 'api.jquery.js' | shopify_asset_url }}" defer="defer"></script><!--<![endif]-->
  <!--[if lte IE 9]><script src="{{ 'api.jquery.js' | shopify_asset_url }}"></script><![endif]-->

  <!--[if (gt IE 9)|!(IE)]><!--><script src="{{ 'shop.js' | asset_url }}" defer="defer"></script><!--<![endif]-->
  <!--[if lte IE 9]><script src="{{ 'shop.js' | asset_url }}"></script><![endif]-->
  
добавляем в assets shop.js.liquid

в header.liquid прописываем qty
и
добавляем подключение миникарты 
  <pre>
<a href="" class="site-header__cart">
  <span>{{ 'layout.cart.title' | t }}</span>

    <div id="CartCount" class="site-header__cart-count">
      <span>
        {% if cart.item_count > 0 %}
          {{ cart.item_count }}
        {% endif %}
      </span>
      <span class="icon__fallback-text desktop-hidden">{{ 'layout.cart.items_count' | t: count: cart.item_count }}</span>
    </div>
</a>
{% include 'minicart' %}
</pre>
  
добавляем файл миникарты в snippets

в форму продукта http://prntscr.com/jeujm6
  
  <input type="hidden" name="return_to" value="back" />
  
  для сабмита дописываем http://prntscr.com/jeuk6k
  
  onclick="Shopify.addItemFromForm('product_form_{{product.id}}'); return false;"
  
  
  готово
