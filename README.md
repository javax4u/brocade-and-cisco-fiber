
## brocade-and-cisco-fiber
#### What is BB metrics and what would be the acronym for    it ?
To prevent a target device (either host or storage) from being overwhelmed with frames, the Fibre Channel architecture provides flow-control mechanisms that are based on a system of credits. Each of these credits represents the ability of the device to accept additional frames. If a recipient issues no credits to the sender, no frames can be sent. Pacing the transport of subsequent frames that is based on the credit system helps prevent the loss of frames and reduces the frequency of entire Fibre Channel sequences needing to be retransmitted across the link.

If the number of buffer credits available for use within each port group is limited, configuring buffer credits for extended links may affect the performance of the other ports in the group that is used for core-to-edge connections. You must balance the number of long-distance ISL connections and core-to-edge ISL connections within a switch.

#### Is it applicable for all type of ports ?
No! Buffer-limited operations are supported for the static mode (LS) and dynamic mode (LD) extended **ISL** (Inter Switch Links) modes only.

#### Please tell OID for it using Brocade switch

#### What happens if there are not enough BB_Credits available?

-   Traffic can still flow in an FC network when insufficient buffers are available. They will just operate at slower line rates. This condition is known as BB_Credit starvation and will still allow traffic to flow as long as BB_Credits are not lost.
-   In fact, if a BB_Credit pool reaches zero, the port can no longer send frames until the credits are replenished or until the link is reset.
-   Fabric Segmentation might occur if BB_Credits do not match on each end of the link and that might cause the inter switch links to not come up. Check the error messages in the logs at both ends and determine why the ISL is failing to come up.

**Note:**  If a given implementation has a high percentage of FC frames of sizes significantly lesser than the maximum size, then more BB_Credits might be required.
