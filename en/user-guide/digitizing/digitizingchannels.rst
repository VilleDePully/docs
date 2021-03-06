Digitizing Channels 
===============================

General
-------
Disable the Reuse last entered attribute values option (Settings -> Options -> Digitizing) because it will stop your second new record. This bug will be corrected at least in QGIS 3.0.

QGEP has a wizard to correctly build channels and connect them to wastewater structures respectively to wastewater nodes or other reaches (building up the topology for waste water nodes and reaches).

.. figure:: images/wizard_data_entry.jpg

.. figure:: images/wizard_data_entry_reach.jpg

.. attention:: Start digitizing in the direction of the flow by starting with the
  **from manhole node** and finishing with the **to manhole node**. 

.. Note:: There is no tool yet to change the flow direction (topology), so try to make it right from the beginning.

Digitizing
----------

* In digitizing mode the cursor will automatically snap to the nearest cover or reach.
  When left clicking a line starts to draw.

.. figure:: images/wizard_data_entry_reach_with_new_cursor.jpg

* With further left clicks anywhere you can define intermediary points of the reach progression.
  You can also directly select another manhole to draw a straight channel.

.. figure:: images/wizard_data_entry_reach_with_new_cursor2.jpg

* You can finish digitizing the line by right clicking. This will make the **vw_qep_reach** form appear.

.. figure:: images/wizard_wastewater_structure_reach_form.jpg

.. note:: Keep in mind that the finishing point of the line is the last point where you **left** clicked.
  Thus, for digitizing a simple line with 2 points you need two **left clicks** to digitize the line and one
  **right click** to finish the line digitizing. 

* Add the attributes on the **General** tab. For the profile type you will get a list of defined profiles.
  You can edit those in **od_pipe_profile** table.

.. figure:: images/wizard_wastewater_structure_reach_form_profiles.jpg


* When finished, then click the **OK** button. 

.. figure:: images/wizard_wastewater_structure_reach_form_data_ok.jpg

* Save the information of this layer by stopping the data entry wizard.

.. figure:: images/stop_data_entry.jpg

* You can re-edit your object selecting the edit mode and then click with the info cursor on the object you want to edit.
* If you do not select the edit mode, you can just look add the existing data.

.. figure:: images/reach_info_reach.jpg

* For detailed information about editing see the :ref:`editing-data` chapter.


Further attributes and classes
------------------------------

When a line object is digitized a series of steps take place in the background in the QGIS database:

* an new object is added in the **wastewater structure** class (``od_wastewater_structure``)
* a new object is added and linked in the **channel** subclass (``od_channel``)
* two new reach point objects are added and linked to the reach (**rp_from_node**, **rp_to_node**)

.. figure:: images/wizard_wastewater_structure_reach_form_reach_points.jpg

* a new reach object is generated in the **wastewater network elements** class (``od_wastewater_networkelement``)
  and its subclass **reach** (``od_reach``)



TO DO Documentation
---------------------

* take more from GEPView-Howto 1.2. Chapter 4.2)
