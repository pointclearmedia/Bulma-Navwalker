# Bulma Navwalker

## To use
1) Create a Primary Menu, (rename to "primary" and tick the checkbox)
![Image for Creating a Primary Menu](https://lh3.googleusercontent.com/fife/ABSRlIqbyTKbfwbUawg9z1jp41rNFS4YX0ce_Wa_VHL6529yO0krs0RNpGU4O7rT4ipGKhIoP9tjBWgAMHOcb01P2yUBGJCCrmWHbqbVvxuDcT2j-L2RyVnVEA-TRFvsbj2S4MDmDFe4XY8OIgw21B8P243kAqoNhxVJhoucj9RTImhQJJ7b8nfDyk6R4zHdWBryKSQH2HMljjxe-X3mkwBtgCSW1nnFP8gWisMQDtqpMN9dhpimGq_qtu-kQbKhPv_gA8fIrShLQiDj1vRwjhC3Pn8DuuTHVTSIkGEjjIW_-xx9eHpO0RWk5Zdo4QpiYYYkFI2671JMgrUgB7JYI6J_AqHoSRmWplFGMTuWIJOUQ_Jq0-ziZVZzvTdXijY5Ib3n2uYzK5VkRAVGhdSxQmPD9NJpDUzpioulZY-Aw_S7gaDSa_w4p3WnN-U8ygB86ow5RHE8CDSvjQj-FZSlLfDmde-IZjc7ho0NHf5zUZ36ERng-Zxs5qTmCeT84yKl7hbM7VLTgbRsczH3Hao3rxSPtGznTufeGxc7CZlXxh--O91PZ92NmWYH21V8o7kJg-wI0mgT8u9JZi0p7S_MhaQSErQ1ew7IxWzddFlkkICNCMse_iBRZR9hMGtqvrn4VzLKe4r47qL54A1an4wK6yUetj1c-3szdivbW5exs35SRASTBT29TdgtY4KcagwJpvCGeWjb2fGvl0QNUQj1GtSezzn_YexvM0qhzA=w1362-h605-ft)
2) place navwalker.php in your WordPress theme folder /wp-content/your-theme/
3) To use Bulma-navwalker add these lines to your functions.php
```
require_once('navwalker.php');
register_nav_menus( array(
    'primary' => __( 'Primary Menu', 'primary' ),
) );
```
4) Copy this to your header
```
<div>
<nav class="navbar" role="navigation" aria-label="main navigation">
  <div class="navbar-brand">
    <a class="navbar-item" href="https://bulma.io">
      <img src="https://bulma.io/images/bulma-logo.png" width="112" height="28">
    </a>

    <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
      <span aria-hidden="true"></span>
    </a>
  </div>

  <div class="navbar-menu">
  
  <?php wp_nav_menu( array( 
      'theme_location'    => 'primary_menu',
      'menu_id'           => 'primary-menu',
      'depth'             => 0,
      'container'         => 'div',
      'container_class'   => 'navbar-start',
      'items_wrap'        => '%3$s',
      'walker'            => new Navwalker())
  ); ?>

    <div class="navbar-end">
      <div class="navbar-item">
        <div class="buttons">
          <a class="button is-primary">
            <strong>Sign up</strong>
          </a>
          <a class="button is-light">
            Log in
          </a>
        </div>
      </div>
    </div>
  </div>
</nav>
</div>
```
5) To make the nav-burgers work add this to the end of the body
```
<script>
    document.addEventListener('DOMContentLoaded', () => {
        
        // Get all "navbar-burger" elements
        const $navbarBurgers = Array.prototype.slice.call(document.querySelectorAll('.navbar-burger'), 0);

        // Check if there are any navbar burgers
        if ($navbarBurgers.length > 0) {

            // Add a click event on each of them
            $navbarBurgers.forEach( el => {
                el.addEventListener('click', () => {

                // Get the target from the "data-target" attribute
                const target = el.dataset.target;
                const $target = document.getElementById(target);

                // Toggle the "is-active" class on both the "navbar-burger" and the "navbar-menu"
                el.classList.toggle('is-active');
                $target.classList.toggle('is-active');
                });
            });
        }
    });
</script>
```

# Congratulations you are now using Bulma!
You can thank me by connecting with me in LinkedIn! https://www.linkedin.com/in/carlooperio/

# Troubleshooting
1) Error: in_array(Line 49) occurs when first step is skipped. I've realized that I have not included that part in this readme.
