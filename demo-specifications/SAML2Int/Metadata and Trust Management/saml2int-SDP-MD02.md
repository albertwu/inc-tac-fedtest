# SAML2Int SDP-MD02

## Statement
Consumption of metadata MUST be contingent on verification of a signature (STRONGLY RECOMMENDED) or TLS server certificate. It MUST be possible to communicate changes to the keys within the metadata without also changing the key used to establish trust in the metadata.

_In most cases, this requirement implies that a key communicated via metadata will not also be used to sign and verify the same metadata, but it is possible to construct scenarios in which this may happen if metadata verification relies on a chain of certificates signed by an ultimately trusted Certificate Authority. The details of such an approach are beyond the scope of this document._

## Testing Objective

1. An entity participating in a ~~federated~~ InCommon SAML SSO tranaction can verify that the entity metadata it retrieves from the InCommon metadata registry is properly signed by the InCommon Federation.

## Definitions

| Term | Defintion |
| ------- | ---------------------------------------------- |
| Subject | The SAML entity undergoing metadata validation. The entity may be an IdP or an SP. |
| | |


## Preconditions

1. The Subject has successfully retrieved testing entity metadata from the (test) InCommon metadata registry. (todo: insert reference to the download test)
2. The Subject has sussessfully retrieved the metadata signing certificate from its published location. (todo: provide instruction to signing certificate loation)

## Test A: A. Verifying signature: signature is correct.

todo: what does the entity do to validate signature?

### Test A Evaluation Criteria 

This is a pass/fail evaluation. 

The Subject **passes** Test A if: 
1. it correctly calculates the signature digest from the metadata, *and*
2. it correctly recognizes the calcuated digest matches the supplied signature and accepts the metadata as a properly signed metadata.

The Subject **fails** Test A otherwise.

## Test B. Verifying signature: signature is incorrect or missing.

todo: what does the entity do to validate signature?

### Test B Evaluation Criteria 

This is a pass/fail test. 

The Subject passes if:

1. if the signature is missing: the Subject recognizes the metadata is missing a signature and rejects the metadata. Alternatively, 
2. if the signature is present: the Subject correctly calculates the signature digest from the metadata, *and*
3. it correctly recognizes the calcuated digest does not match the supplied signature and accepts the metadata as a properly signed metadata.

## Acceptance

The Subject **passes** this test if it passes both Test A and B. Otherwise, it **fails** this test.


## Postcondition

N/A





