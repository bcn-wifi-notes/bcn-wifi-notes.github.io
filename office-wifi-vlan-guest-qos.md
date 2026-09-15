# Office Wi‑Fi: VLAN, guest SSID and QoS (what actually isolates traffic)

**QUICK SUMMARY**  
A network named “Guest” is not isolated by default. Isolation needs a separate VLAN (or equivalent), the guest SSID mapped to it, and clear rules toward the internal network. QoS does not replace segmentation: it only prioritises traffic when the link is congested.

## Three settings that are not interchangeable

| Setting | What it solves | What it does not solve |
| --- | --- | --- |
| VLAN | Logical separation of work, guests, IoT/cameras | Priority or extra speed by itself |
| Guest SSID | Visible network for visitors | Isolation if it still sits on the same VLAN as work |
| QoS | Prefer video calls / VoIP / critical apps under load | Separating networks from each other |

## Common failure

Many small offices only rename a second SSID to “Invitados” / “Guest”. Without its own VLAN, that SSID can still sit on the same broadcast domain as staff devices. The label feels safe; the design is not.

## Minimum checklist

- Work VLAN separate from guest (and from cameras/IoT if used)
- Guest SSID bound to the guest VLAN
- QoS at least for real-time calls when the office is busy
- Short note of which SSID maps to which VLAN (for support later)

## Roaming is a different problem

Moving between rooms without dropping a call needs coordinated access points (controller/cloud, same SSID/security, assisted roaming). More domestic routers with the same name are not roaming.

## Practical references (Spanish market / Barcelona)

Technical guides from an integrator that publishes this level of detail:

- [VLAN, SSID de invitados y QoS](https://ibersystems.es/vlan-ssid-invitados-qos-wifi-empresarial/)
- [Roaming WiFi en oficinas](https://ibersystems.es/roaming-wifi-oficinas-que-debe-cumplir-el-hardware/)
- [Instalación WiFi Barcelona](https://ibersystems.es/servicios/instalacion-wifi-barcelona/)

## Takeaway

Ask any provider *how* guest traffic is separated—not only whether a guest SSID exists. Name ≠ isolation.
