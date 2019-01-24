# Various BMIR Helper Stuff

Here's some stuff that I've found useful for my work with BMIR.

## Table of Contents

1. `voip-two-way/` &mdash; Helpers for setting up a two-way
   "[automatic ringdown](https://en.wikipedia.org/wiki/Ringdown#Non-operator_use)"
   module for our broadcast desk. Interface into the broadcast deskboard is a
   ~~[JK Audio AutoHybrid](http://www.jkaudio.com/autohybrid.htm)~~ [JK Audio Broadcast Host](https://www.jkaudio.com/broadcast-host.htm), and hack for an old
   VOIP ATA, described below.

    - [`voip-two-way-howto.tar.xz`](voip-two-way/voip-two-way-howto.tar.xz): Tarball of archived
      HTML file explaining how to set up a two-way, ringing, ringdown or "walkie-talkie"
      style phone line with an old [Linksys PAPT2-NA](https://www.amazon.com/Linksys-PAP2T-NA/dp/B000Q7PDW2),
      which I just happened to have. _(See: [the original how-to on
      instructables.com](https://www.instructables.com/id/Hack-a-VOIP-Box-Into-a-Telephone-Intercom/).)_

        - Note to avoid weird, annoying ghost rings after hangup:

            - ~~with a [Cortelco 2500](https://www.amazon.com/dp/B002LLH3Q0) and the
              [Panasonic KX-TG6592T](https://www.amazon.com/gp/B004N4FE64), I had to change
              the _"Dial Plan"_ on line 1 and line 2 to `(S3<:line2@127.0.0.1:5061>)` and
              `(S3<:line1@127.0.0.1:5060>)`, respectively, ie `S0` to `S3` to have a 3 second
              delay before dialing the other line.~~

            - No need to change the dial plan! I figure it out, however the _"VM tone detect"_
              feature on the [Panasonic KX-TG6592T](https://www.amazon.com/dp/B004N4FE64/)
              must be turned off. (Wow this one sucked to debug.) On the handset go:

                - `MENU > Initial Setting > Voice mail > VM tone detect` and set to `OFF`.
                - See manual: [`KX-TG6592-manual.pdf`](voip-two-way/KX-TG6592-manual.pdf)

## License

This project is licensed under the MIT License &mdash; see the
[`LICENSE`](LICENSE) file for details.

