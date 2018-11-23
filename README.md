прописываем подключения
<pre>
<code>
  {{ 'api.jquery.js' | shopify_asset_url | script_tag }}
  {{ 'shop.js' | asset_url | script_tag }}
</code>
</pre>

добавляем в assets shop.js.liquid

в header.liquid прописываем qty
и
добавляем подключение миникарты 
<pre>
  <code>
  <a href="#" class="site-header__cart">
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
  </code>
</pre>
  
добавляем файл миникарты в snippets

в форму продукта http://prntscr.com/jeujm6
<pre>
  <code>
    <input type="hidden" name="return_to" value="back" />
  </code>
</pre>
  для сабмита дописываем http://prntscr.com/jeuk6k
<pre>
  <code>
    onclick="Shopify.addItemFromForm('product_form_{{product.id}}'); return false;"
  </code>
</pre>
  
готово
