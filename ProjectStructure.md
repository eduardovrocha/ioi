lib/
│
├── core/                   # Núcleo compartilhado: serviços, temas, constantes, utils
│   ├── providers/          # Ex: dio_client_service.dart, logger.dart, etc
│   ├── theme/              # Paleta de cores, estilos de texto, dimensões
│   ├── utils/              # Funções auxiliares
│   └── widgets/            # Widgets reutilizáveis globais (botões, loaders etc)
│
├── features/
│   ├── about/
│   │   ├── views/              # about_view.dart
│   │   └── components/         # scrollable_about_content.dart
│
│   ├── access/
│   │   ├── views/              # access_view.dart
│   │   ├── providers/          # access_provider.dart
│   │   └── components/         # password_confirmation_field_component.dart
│
│   ├── auction/
│   │   ├── views/              # show_auction_component.dart
│   │   └── components/
│   │       ├── auction_action_component.dart
│   │       ├── bid_history_component.dart
│   │       ├── bid_history_item_component.dart
│   │       └── count_down_timer_component.dart
│
│   ├── content/
│   │   ├── views/              # content_view.dart
│   │   ├── providers/          # content_provider.dart
│   │   ├── models/             # comment_model.dart
│   │   └── widgets/
│   │       ├── add_comment_widget.dart
│   │       ├── coin_counter_action_component.dart
│   │       ├── content_settings_edit_component.dart
│   │       ├── image_with_filters_widget.dart
│   │       ├── manage_content_view_component.dart
│   │       ├── manage_open_content_component.dart
│   │       ├── show_auction_component.dart
│   │       ├── show_open_content_component.dart
│   │       └── user_post_card_widget.dart
│
│   ├── engine/
│   │   ├── views/              # engine_view.dart
│   │   └── widgets/
│   │       ├── content_album_gallery_component.dart
│   │       ├── content_album_promotion_component.dart
│   │       ├── content_auction_component.dart
│   │       ├── content_open_component.dart
│   │       └── content_restricted_component.dart
│
│   ├── entrance/
│   │   ├── views/              # entrance_view.dart
│   │   ├── providers/          # entrance_provider.dart
│   │   └── widgets/
│   │       ├── navigation_view_component.dart
│   │       └── components/
│   │           ├── color.dart
│   │           ├── model.dart
│   │           ├── paint.dart
│   │           └── text_style.dart
│
│   ├── financial/
│   │   ├── views/              # financial_view.dart
│   │   ├── providers/          # financial_provider.dart
│   │   ├── models/             # invoice.dart
│   │   └── components/
│   │       ├── credit_coin_purchase_widget.dart
│   │       ├── invoice_card_component.dart
│   │       ├── payment_form_component.dart
│   │       ├── savings_card_component.dart
│   │       ├── scrollable_financial_content.dart
│   │       ├── transaction_history_item_component.dart
│   │       └── transaction_history_list_component.dart
│
│   ├── home/
│   │   ├── views/              # home_view.dart
│   │   ├── providers/          # home_provider.dart
│   │   └── widgets/
│   │       ├── components/
│   │       │   ├── following/
│   │       │   │   └── following_profile_last_content.dart
│   │       │   ├── suggestion/
│   │       │   │   ├── globe/
│   │       │   │   │   └── suggesting_profile_last_content.dart
│   │       │   │   └── timeLine/
│   │       │   │       └── example/
│   │       │   │           └── showcase_timeline.dart
│   │       ├── following_scrollable_component.dart
│   │       └── suggestion_scrollable_component.dart
│
│   ├── invite/
│   │   └── views/              # invite_view.dart
│
│   ├── notification/
│   │   └── views/              # notification_view.dart
│
│   ├── profile/
│   │   ├── views/              # profile_view.dart
│   │   ├── providers/          # profile_provider.dart
│   │   ├── components/
│   │   │   ├── about_me_component.dart
│   │   │   ├── comment_scrollable_component.dart
│   │   │   ├── followers_scrollable_component.dart
│   │   │   ├── followings_scrollable_component.dart
│   │   │   ├── gallery_scrollable_component.dart
│   │   │   ├── history_scrollable_component.dart
│   │   │   ├── mention_scrollable_component.dart
│   │   │   └── network_scrollable_component.dart
│   │   └── shared/
│   │       ├── comment_card_component.dart
│   │       ├── follower_card_component.dart
│   │       ├── following_card_component.dart
│   │       ├── image_grid_list_component.dart
│   │       ├── profile_menu_component.dart
│   │       ├── show_dash_content_component.dart
│   │       ├── show_edit_data_component.dart
│   │       ├── show_edit_date_component.dart
│   │       └── show_open_comment_component.dart
│
│   ├── reward/
│   │   ├── views/              # reward_view.dart
│   │   ├── providers/          # reward_provider.dart
│   │   └── components/
│   │       ├── content_invoice_component.dart
│   │       ├── content_invoice_detail_component.dart
│   │       ├── scrollable_content_rewards_component.dart
│   │       └── scrollable_contents_component.dart
│
│   ├── settings/
│   │   ├── views/              # settings_view.dart
│   │   ├── providers/          # settings_provider.dart
│   │   └── components/
│   │       ├── bank_dropdown_component.dart
│   │       ├── config_options_widget.dart
│   │       ├── geolocation_widget.dart
│   │       ├── scrollable_settings_content.dart
│   │       ├── show_settings_section_component.dart
│   │       ├── upload_documents_widget.dart
│   │       ├── view_settings_shared_data_widget.dart
│   │       └── view_shared_preferences_data_widget.dart
│
│   └── splash/
│       ├── views/              # splash_view.dart
│       └── providers/          # splash_provider.dart
│
├── main.dart
