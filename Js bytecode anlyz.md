Js bytecode anlyz

Ttl abt  cmd  cnt  150

Js   Ignition Bytecodes字节码  类型转换有哪些指令？





Ignition Bytecodes


载累加器 cmd10


https://cs.chromium.org/chromium/src/v8/src/interpreter/bytecodes.h
Extended width operands 

Wide
ExtraWide
Loading the accumulator

LdaZero
LdaSmi
LdaUndefined
LdaNull
LdaTheHole
LdaTrue
LdaFalse
LdaConstant
Globals 全局变量 +上下文 cmd10


LdaGlobal
LdaGlobalInsideTypeof
StaGlobalSloppy
StaGlobalStrict
Context Operations

PushContext
PopContext
LdaContextSlot
LdaImmutableContextSlot
LdaCurrentContextSlot
LdaImmutableCurrentContextSlot
StaContextSlot
StaCurrentContextSlot
Load-Store lookup slots  加载-存储查找槽 cmd20


LdaLookupSlot
LdaLookupContextSlot
LdaLookupGlobalSlot
LdaLookupSlotInsideTypeof
LdaLookupContextSlotInsideTypeof
LdaLookupGlobalSlotInsideTypeof
StaLookupSlot
Register-accumulator transfers

Ldar
Star
Register-register transfers

Mov
Property loads (LoadIC) operations

LdaNamedProperty
LdaKeyedProperty
Operations on module variables

LdaModuleVariable
StaModuleVariable
Propery stores (StoreIC) operations

StaNamedPropertySloppy
StaNamedPropertyStrict
StaNamedOwnProperty
StaKeyedPropertySloppy
StaKeyedPropertyStrict
StaDataPropertyInLiteral
CollectTypeProfile
Binary Operators 二元运算符 三元 cmd30


Add
Sub
Mul
Div
Mod
BitwiseOr
BitwiseXor
BitwiseAnd
ShiftLeft
ShiftRight
ShiftRightLogical
Binary operators with immediate operands

AddSmi
SubSmi
MulSmi
DivSmi
ModSmi
BitwiseOrSmi
BitwiseXorSmi
BitwiseAndSmi
ShiftLeftSmi
ShiftRightSmi
ShiftRightLogicalSmi
Unary Operators

Inc
Dec
ToBooleanLogicalNot
LogicalNot
TypeOf
DeletePropertyStrict
DeletePropertySloppy
GetSuperConstructor operator

GetSuperConstructor
Call operations 调用操作 cmd10


CallAnyReceiver
CallProperty
CallProperty0
CallProperty1
CallProperty2
CallUndefinedReceiver
CallUndefinedReceiver0
CallUndefinedReceiver1
CallUndefinedReceiver2
CallWithSpread
CallRuntime
CallRuntimeForPair
CallJSRuntime
Intrinsics

InvokeIntrinsic
Construct operators

Construct
ConstructWithSpread
Test Operators  ceshi cmd10 .other20

TestEqual
TestEqualStrict
TestLessThan
TestGreaterThan
TestLessThanOrEqual
TestGreaterThanOrEqual
TestEqualStrictNoFeedback
TestInstanceOf
TestIn
TestUndetectable
TestNull
TestUndefined
TestTypeOf
Cast operators

ToName
ToNumber
ToObject
Literals

CreateRegExpLiteral
CreateArrayLiteral
CreateEmptyArrayLiteral
CreateObjectLiteral
Closure allocation

CreateClosure
Context allocation

CreateBlockContext
CreateCatchContext
CreateFunctionContext
CreateEvalContext
CreateWithContext
Arguments allocation

CreateMappedArguments
CreateUnmappedArguments
CreateRestParameter
Control Flow -- 控制cmd30
carefully ordered for efficient checks

[Unconditional jumps]

JumpLoop
[Forward jumps]

Jump
[Start constant jumps]

JumpConstant
[Conditional jumps]

[Conditional constant jumps]

JumpIfNullConstant
JumpIfNotNullConstant
JumpIfUndefinedConstant
JumpIfNotUndefinedConstant
JumpIfTrueConstant
JumpIfFalseConstant
JumpIfJSReceiverConstant
[Start ToBoolean jumps]

JumpIfToBooleanTrueConstant
JumpIfToBooleanFalseConstant
[End constant jumps]

[Conditional immediate jumps]

JumpIfToBooleanTrue
JumpIfToBooleanFalse
[End ToBoolean jumps]

JumpIfTrue
JumpIfFalse
JumpIfNull
JumpIfNotNull
JumpIfUndefined
JumpIfNotUndefined
JumpIfJSReceiver
Smi-table lookup for switch statements

SwitchOnSmiNoFeedback
Complex flow control For..in

ForInPrepare
ForInContinue
ForInNext
ForInStep
Perform a stack guard check

StackCheck
Update the pending message

SetPendingMessage
Non-local flow control

Throw
ReThrow
Return
ThrowReferenceErrorIfHole
ThrowSuperNotCalledIfHole
ThrowSuperAlreadyCalledIfNotHole
Generators

RestoreGeneratorState
SuspendGenerator
RestoreGeneratorRegisters
Debugger   cmd10

Debugger
Debug Breakpoints

DebugBreak0
DebugBreak1
DebugBreak2
DebugBreak3
DebugBreak4
DebugBreak5
DebugBreak6
DebugBreakWide
DebugBreakExtraWide
Block Coverage

IncBlockCounter
Illegal bytecode (terminates execution)

Illegal

