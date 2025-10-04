To inherit the sale module

## Create Module Structure
Directory structure for the custom module:

```md
custom_sale_extension/
├── __init__.py
├── __manifest__.py
├── models/
│   ├── __init__.py
│   └── sale_order.py
└── views/
    └── sale_order_views.xml
```

## `__manifest__.py

``` python
{
    'name': 'Custom Sale Extension',
    'version': '17.0.1.0',
    'summary': 'Extends the Sale module with custom features',
    'description': 'This module adds a custom field to the Sale Order model.',
    'author': 'VarApps',
    'depends': ['sale'],
    'data': [
        'views/sale_order_views.xml',
    ],
    'installable': True,
    'application': False,
}

```

## `models/__init__.py`

``` python
from . import sale_order
```

## `models/sale_order.py`

``` python
from odoo import models, fields

class SaleOrder(models.Model):
    _inherit = 'sale.order'

    x_custom_field = fields.Char(string="Custom Field")
```

## `views/sale_order_views.xml`

``` xml
<odoo>
    <record id="view_order_form_inherit_custom" model="ir.ui.view">
        <field name="name">sale.order.form.inherit.custom</field>
        <field name="model">sale.order</field>
        <field name="inherit_id" ref="sale.view_order_form"/>
        <field name="arch" type="xml">
            <sheet position="inside">
                <group>
                    <field name="x_custom_field"/>
                </group>
            </sheet>
        </field>
    </record>
</odoo>
```