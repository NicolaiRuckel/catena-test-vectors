# Catena Test Vectors

This are test vectors for Catena implementations.

Every test vector is an array of tests
cases, each containing the inputs for the function in `inputs` and the
expected outputs in `outputs`.
Strings in these files have to be interpreted as hex encoded big endian byte
strings with two characters for a byte unless stated otherwise.

Each file uses up to one Catena instance for every contained test case, which is
specified in the file name. These instances are:

- `Any`:
Any Catena instance with H = Blake2b and H' = Blake2b-1
- `Any Full`:
Any Catena instance with H = H' = Blake2b
- `Butterfly`
- `Butterfly Full`
- `Butterfly Reduced`:
Catena Butterfly with `g_low` = `g_high` = 9
- `Butterfly Reduced Different G`:
Catena Butterfly with `g_low` = 8 and `g_high` = 9
- `Butterfly Full Reduced`:
Catena Butterfly Full with `g_low` = `g_high` = 9
- `Dragonfly`
- `Dragonfly Full`
- `Dragonfly Reduced`:
Dragonfly with `g_low` = `g_high` = 14
- `Dragonfly Full Reduced`:
Dragonfly Full with `g_low` = `g_high` = 14
- `Stonefly`
- `Stonefly Full`
- `Stonefly Reduced`:
Stonefly with `g_low` = `g_high` = 9
- `Stonefly Full Reduced`:
Stonefly Full with `g_low` = `g_high` = 9
- `MartyMcFly`
- `MartyMcFly-Full`
- `MartyMcFly Reduced`:
MartyMcFly with `g_low` = `g_high` = 9
- `Mydasfly`
- `Mydasfly Full`
- `Mydasfly Reduced`:
Mydasfly with `g_low` = `g_high` = 9
- `Mydasfly Full Reduced`:
Mydasfly Full with `g_low` = `g_high` = 9
- `Lanternfly`
- `Lanternfly Full`
- `Lanternfly Reduced`
Lanternfly with `g_low` = `g_high` = 9
- `Lanternfly Full Reduced`:
Lanternfly Full with `g_low` = `g_high` = 9
- `Horsefly`
`Horsefly Full`
`Horsefly Reduced`:
Horsefly with `g_low` = `g_high` = 13
- `Horsefly Full Reduced`:
Horsefly Full with `g_low` = `g_high` = 13

The purpose of the tests with the reduced Catena instances is to ensure that all
tests of all test vectors can run in acceptable time, even in the dynamically
typed languages.

Tests that do not need an instance of Catena have nothing appended to their
file names.

## Blake2b
Test files:
- `blake2b.json`

## Blake2b-1
Test files:
-  `blake2b1.json`

The tests are expected to run from first to last with the same instance of
Blake2b-1. The field `reset` indicates wether or not the `reset`
function of the Blake2b-1 instance has to be called before the test.

## CF_Argon2
Test files for the complete compression function:
-  `cfArgon2Gb.json`
-  `cfArgon2Gl.json`

Test files for G_L and G_B:
-  `gB.json`
-  `gL.json`

Test files for the $permute$ function:
-  `permuteGb.json`
-  `permuteGl.json`
-  `permuteGbHex.json`
-  `permuteGlHex.json`

The test files with the `Hex` suffix are the test cases as the respective
files without the suffix. The hex versions have the 64 bit integers encoded as
hex values for the JavaScript implementation because JavaScript has no built-in
64 bit integer type.

## H_first
Test files:
-  `hFirstAny.json`

## Bit-Reversal Graph
Test files for index function:
-  `brgIndex.json`

Test files for full graph:
-  `brgAny.json`
-  `brgAnyFull.json`

## Shifted Bit-Reversal Graph
Test files for index function:
-  `sbrgIndex.json`

Test files for full graph:
-  `sbrgAny.json`
-  `sbrgAnyFull.json`

## Gray-Reverse Graph
Test files for index function:
-  `grgIndex.json`

Test files for full graph:
-  `grgAny.json`
-  `grgAnyFull.json`

## Double Butterfly Graph
Test files for index function:
-  `dbhIndex.json`

Test files for full graph:
-  `dbhAny.json`
-  `dbhAnyFull.json`

## Saltmix
Test files:
-  `saltmix.json`

The input `hash` is the hashed salt, appended four times.

## Phi
Test file for the LSB index function:
- `lsbIndex.json`

## H_init
Test files:
- `hInitAnyFull.json`

The output tuple `v` is `[v_-2, v_-1]`.

## Tweak
Test files:
- `tweakButterfly.json`
- `tweakButterflyFull.json`
- `tweakDragonfly.json`
- `tweakDragonflyFull.json`

The field `aData` is an UTF-8 string.

## Flap
Test files:
- `flapButterfly.json`
- `flapButterflyFull.json`
- `flapDragonfly.json`
- `flapDragonflyFull.json`

## Catena
Test files:
- `catenaButterfly.json`
- `catenaButterflyFull.json`
- `catenaButterflyReduced.json`
- `catenaButterflyFullReduced.json`
- `catenaDragonfly.json`
- `catenaDragonflyFull.json`
- `catenaDragonflyReduced.json`
- `catenaDragonflyFullReduced.json`
- `catenaHorsefly.json`
- `catenaHorseflyFull.json`
- `catenaHorseflyReduced.json`
- `catenaHorseflyFullReduced.json`
- `catenaLanternfly.json`
- `catenaLanternflyFull.json`
- `catenaLanternflyReduced.json`
- `catenaLanternflyFullReduced.json`
- `catenaMartyMcFly.json`
- `catenaMartyMcFlyFull.json`
- `catenaMydasfly.json`
- `catenaMydasflyFull.json`
- `catenaMydasflyReduced.json`
- `catenaMydasflyFullReduced.json`
- `catenaStonefly.json`
- `catenaStoneflyFull.json`
- `catenaStoneflyReduced.json`
- `catenaStoneflyFullReduced.json`

The non-reduced tests implicitly test the correct parameters of the default
instances and variants.

## Key Derivation
Test files:
- `keyDerivationButterfly.json`
- `keyDerivationButterflyFull.json`
- `keyDerivationButterflyReduced.json`
- `keyDerivationDragonfly.json`
- `keyDerivationDragonflyFull.json`
- `keyDerivationDragonflyReduced.json`

## Keyed Hashing
Test files:
- `keyedHashButterfly.json`
- `keyedHashButterflyFull.json`
- `keyedHashButterflyReduced.json`
- `keyedHashDragonfly.json`
- `keyedHashDragonflyFull.json`
- `keyedHashDragonflyReduced.json`
- `keyedHashMartyMcFly.json`
- `keyedHashMartyMcFlyFull.json`

## Server Relief
Test files for client side:
- `serverReliefClientButterflyFullReduced.json`
- `serverReliefClientButterflyFullReducedDifferentG.json`
- `serverReliefClientButterflyReduced.json`
- `serverReliefClientDragonflyFullReduced.json`
- `serverReliefClientDragonflyReduced.json`
- `serverReliefClientMartyMcFly.json`
- `serverReliefClientMartyMcFlyFull.json`

The test case `serverReliefClientButterflyReducedDifferentG.json` is
needed to test the loop in the server relief, which is skipped if `g_low` =
`g_high`.

Test files for server side:
- `serverReliefServerButterflyFullReduced.json`
- `serverReliefServerButterflyReduced.json`
- `serverReliefServerDragonflyFullReduced.json`
- `serverReliefServerDragonflyReduced.json`

## Client-Independent Update
Test files:
- `ciUpdateButterfly.json`
- `ciUpdateButterflyFull.json`
- `ciUpdateDragonfly.json`
- `ciUpdateDragonflyFull.json`
- `ciUpdateDragonflyReduced.json`

## Keyed Client-Independent Update
Test files:
- `ciUpdateKeyedDragonflyReduced.json`

## Proof of Work
Test files for the server side:
- `proofOfWorkServerPwdButterfly.json`
- `proofOfWorkServerPwdButterflyFull.json`
- `proofOfWorkServerPwdButterflyReduced.json`
- `proofOfWorkServerPwdDragonfly.json`
- `proofOfWorkServerPwdDragonflyFull.json`
- `proofOfWorkServerPwdMartyMcFlyReduced.json`
- `proofOfWorkServerSaltButterfly.json`
- `proofOfWorkServerSaltButterflyFull.json`
- `proofOfWorkServerSaltButterflyReduced.json`
- `proofOfWorkServerSaltDragonfly.json`
- `proofOfWorkServerSaltDragonflyFull.json`
- `proofOfWorkServerSaltMartyMcFlyReduced.json`

Test files for the client side:
- `proofOfWorkClientPwdButterfly.json`
- `proofOfWorkClientPwdButterflyFull.json`
- `proofOfWorkClientPwdButterflyReduced.json`
- `proofOfWorkClientPwdDragonfly.json`
- `proofOfWorkClientPwdDragonflyFull.json`
- `proofOfWorkClientSaltButterfly.json`
- `proofOfWorkClientSaltButterflyFull.json`
- `proofOfWorkClientSaltButterflyReduced.json`
- `proofOfWorkClientSaltDragonfly.json`
- `proofOfWorkClientSaltDragonflyFull.json`

# Changelog

## 2018-04-16
We added experimental test vectors for the new MartyMcFly instance.  We use
`g_low` = `g_high` = 17 for the regular and `g_low` = `g_high` = 23 for the Full
variant.  We used a modified version of DRSample as the graph and no Γ or Φ.
See [Catena-Cpp](https://github.com/medsec/catena-cpp) for a sample
implementation of the MartyMcFly variants.
