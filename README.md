# Signed commits

I am signing my commits now! _Yay!_

## Why?

"_GPG keys are a way to sign and verify work from trusted collaborators._". ([source](https://help.github.com/articles/signing-commits-with-gpg/))

And also that [verified tag looks nice](https://0x0.st/weN.png).

## How?

_Note: not exactly step-by-step tutorial, just a tiny summary._

See https://help.github.com/articles/signing-commits-with-gpg/

I personally set signing up with subkey. If you want to do exactly like I did, then:

- Create new 4096bit RSA subkey
- Save changes
- Get key id by `gpg --keyid-format long --list-keys`
- Optionally do your usual hackery to keep only subkey in your machine (quite many tutorials recommend you to keep gpg keys offline)
- Put public key to your clipboard using `gpg --armor --export <your email> | xsel -ib` and paste it into [GPG key box](https://0x0.st/weq.png) in GitHub.
- Set your signing key and make git sign commits automatically using `git config --global user.signingkey <key id>` and `git config --global commit.gpgsign true`
- Push new commits to your repos and enjoy verified tag
