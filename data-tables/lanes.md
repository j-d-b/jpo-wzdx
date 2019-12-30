# lanes
**Optional**

This table identifies and describes individual lanes within a road event.  

This table is related to the [road_events](/data-tables/road_events.md) table by the foreign key road_event_id.  For every record in the road_event table there may exist one or more record(s) in the lanes table.

This table is related to the [lane_restrictions](/data-tables/lane_restrictions.md) table;  For each record in the lanes table there may exists a one or more records in the lane_restrictions table.  The lane_id field acts as the foreign key in the lanes table.

#### Lanes Table
Data Name|Data Type|Description|Conformance|Notes
-|-|-|-|-|
lane_id|ID|Identifies the lane_info record|Required|Primary key
[road_event_id](/data-tables/road_events.md)|ID|Identifies the road event to which a lane information is related.|Required|Foreign key
lane_edge_reference|Enumeration; Text|The roadside edge from which lane are assigned numbers.|Conditional: required if  lane_number is not null|Counting begins from the edge of the improved surface. See [enumerated fields](https://github.com/usdot-jpo-ode/jpo-wzdx/blob/v2editorial/data-tables/enumerated-fields.md)
lane_number|Non-negative Integer|The number assigned to a lane.|Optional|Assigned by counting from right or left edge of the improved surface. Counting begins from the edge indicated in the lane_edge_reference field. Useful for text to voice translation. Numbering should not include shoulders.
lane_status|Enumeration; Text|Status of the lane for the traveling public|Required|Allowed values: open, closed, shift-left, shift-right, merge-right, merge-left, alternating-one-way. See [enumerated fields](https://github.com/usdot-jpo-ode/jpo-wzdx/blob/v2editorial/data-tables/enumerated-fields.md)
lane_type|Enumeration; Text|A lane descriptor|Required|See [enumerated fields](https://github.com/usdot-jpo-ode/jpo-wzdx/blob/v2editorial/data-tables/enumerated-fields.md)