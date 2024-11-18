---
hide:
  - toc
  - navigation
---

{% import 'tiles.md' as tiles %}

# Contact

{% call tiles.contact_tile_wall() %}

  {{ tiles.contact_tile_image('../images/yashwanth.png', 
                              'Yashwanth Singh M', 
                              'yashwanth.singhm@in.bosch.com') }}
  {{ tiles.contact_tile('Yashwanth<br/>Singh M', 
                        'Organiser<br/>', 
                        '', 
                        'yashwanth.singhm@in.bosch.com', 
                        color='green-slight-fade') }}

  {{ tiles.contact_tile_image('../images/poorvi.png', 
                              'Poorvi Kadakol', 
                              'poorvi.pramodkadakol@in.bosch.com') }}
  {{ tiles.contact_tile('Poorvi<br/>Kadakol', 
                        'Organiser<br/>', 
                        '', 
                        'poorvi.pramodkadakol@in.bosch.com', 
                        color='green-slight-fade') }}
  <!--
  {{ tiles.contact_tile_image('../images/nihal.png', 
                              'Nihal Pasham', 
                              'pasham.nihalgoud@in.bosch.com') }}
  {{ tiles.contact_tile('Nihal<br/>Pasham', 
                        'Rust<br/>Developer', 
                        '', 
                        'pasham.nihalgoud@in.bosch.com', 
                        color='green-slight-fade') }}
  {{ tiles.contact_tile_image('../images/brian.png', 
                              'Brian Dcosta', 
                              'brianfrancisolaf.dcosta@in.bosch.com') }}
  {{ tiles.contact_tile('Brian<br/>Dcosta', 
                        'Rust<br/>Developer', 
                        '', 
                        'brianfrancisolaf.dcosta@in.bosch.com', 
                        color='green-slight-fade') }}
  {{ tiles.contact_tile_image('../images/anand.png', 
                              'Anand Gedam', 
                              'anand.bhauraojigedam@in.bosch.com') }}
  {{ tiles.contact_tile('Anand<br/>Gedam', 
                        'Rust<br/>Developer', 
                        '', 
                        'anand.bhauraojigedam@in.bosch.com', 
                        color='green-slight-fade') }}
  {{ tiles.contact_tile_image('../images/imran.png', 
                              'Imran K', 
                              'imran.khaleelsab@in.bosch.com') }}
  {{ tiles.contact_tile('Imran K<br/>', 
                        'Rust<br/>Developer',
                        '',
                        'imran.khaleelsab@in.bosch.com', 
                        color='green-slight-fade') }}
  {{ tiles.contact_tile_image('../images/sarath.png', 
                              'Sarath Kumar', 
                              'bobbili.sarathkumar@in.bosch.com') }}
  {{ tiles.contact_tile('Sarath<br/>Kumar', 
                        'Rust<br/>Developer',
                        '',
                        'bobbili.sarathkumar@in.bosch.com', 
                        color='green-slight-fade') }}
  -->

{% endcall %}
