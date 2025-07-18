# Creation

Proposers can create a Proposal at any time.

A Proposer **MUST NOT** have more than one active proposal at any time.

The Proposer creates a Proposal Application from the xGov Registry.

Upon Proposal creation, an Open Proposal Fee **MUST** be paid to the xGov Treasury.

The Proposal Application MBR is deducted from the Open Proposal Fee; the remainder
**MUST** be entirely transferred to the Proposal Escrow.

{{#include ../.include/styles.md:note}}
> The xGov Manager **MAY** update the Proposal Fee.

The remainder of the Open Proposal Fee **MUST** cover the MBR of all the Boxes required
by the xGov Committee assigned to the Proposal upon opening.

{{#include ../.include/styles.md:example}}
> Given a Proposer Voter Box size, the Open Proposal Fee amount **SHOULD** be proportional
> to the xGov Committee size. The Voter Box MBR is roughly \\( 0.02 \\) ALGO. Example:
> an xGov Committee of \\( 500 \\) voters requires roughly \\( 10 \\) ALGO of MBR
> to the Proposal Application.

The Proposer **SHOULD** pay the Open Proposal Fee.

The Open Proposal Fee has the following scope:

1. Anti-spam measure;

1. Covering Proposal Escrow Account MBR;

1. Covering Proposal Metadata Box MBR;

1. Covering xGov Committee Boxes MBR (introduced later).

1. Covering xGov Daemon operation fees for the Proposal.

Upon opening the Proposal Draft, the Proposer **MUST** lock in the Proposal Escrow
a percentage of the requested funding amount as a commitment.

{{#include ../.include/styles.md:note}}
> The xGov Manager **MAY** update the percentage of the requested funding amount
> to commit.

The locked amount **SHALL** be either:

- Returned to the Proposer when the Proposal is:

  - Funded or Rejected;
  - Dropped by the Proposer before submission.

- Slashed if the Proposal is blocked with a veto by the xGov Council.

Upon proposal opening, the xGov Committee ID, total members, and total voting power
**MUST** be fetched from the xGov Registry and assigned to the Proposal.

The xGov Daemon **MAY** finalize the Empty Proposal if it becomes stale (the Proposer
does not open a Draft).
