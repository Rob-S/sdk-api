---
UID: NF:traceloggingprovider.TraceLoggingBinary
title: TraceLoggingBinary macro (traceloggingprovider.h)
description:
  TraceLogging wrapper macro that adds a field with binary data to the event.
helpviewer_keywords:
  [
    "TraceLoggingBinary",
    "TraceLoggingBinary macro",
    "tracelogging.traceloggingbinary",
    "traceloggingprovider/TraceLoggingBinary",
  ]
old-location: tracelogging\traceloggingbinary.htm
tech.root: tracelogging
ms.assetid: A1CE1481-7319-41BE-9639-E688365D4628
ms.date: 12/05/2018
ms.keywords:
  TraceLoggingBinary, TraceLoggingBinary macro, tracelogging.traceloggingbinary,
  traceloggingprovider/TraceLoggingBinary
req.header: traceloggingprovider.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows Vista [desktop apps \| UWP apps]
req.target-min-winversvr: Windows Server 2008 [desktop apps \| UWP apps]
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql:
targetos: Windows
req.typenames:
req.redist:
ms.custom: 19H1
f1_keywords:
  - TraceLoggingBinary
  - traceloggingprovider/TraceLoggingBinary
dev_langs:
  - c++
topic_type:
  - APIRef
  - kbSyntax
api_type:
  - HeaderDef
api_location:
  - traceloggingprovider.h
api_name:
  - TraceLoggingBinary
---

# TraceLoggingBinary macro

## -description

[TraceLogging wrapper macro](/windows/desktop/tracelogging/tracelogging-wrapper-macros)
that adds a field with binary data to the event.

## -parameters

### -param pbData [in]

A pointer to the data to be included in the event.

### -param cbData [in]

The size, in bytes, of the data to be included in the event.

#### - name [in, optional]

The name to use for the event field. If provided, the name parameter must be a
string literal (not a variable) and must not contain any '\0' characters. If not
provided, the event field name will be based on _pbData_.

#### - description [in, optional]

The description of the event field's value. If provided, the description
parameter must be a string literal and will be included in the
[PDB](/windows-hardware/drivers/debugger/symbols).

#### - tags [in, optional]

A compile-time constant integer value. The low 28 bits of the value will be
included in the field's metadata. The semantics of this value are defined by the
event consumer. During event processing, this value can be retrieved from the
[EVENT_PROPERTY_INFO](../tdh/ns-tdh-event_property_info.md) Tags field.

## -remarks

`TraceLoggingBinary(pbData, cbData, ...)` can be used as a parameter to an
invocation of a
[TraceLoggingWrite](./nf-traceloggingprovider-traceloggingwrite.md) macro. Each
TraceLoggingBinary parameter adds one field to the event.

TraceLoggingBinary can be specified with 2, 3, 4, or 5 parameters. If a
parameter is not specified, a default will be used. For example,
`TraceLoggingBinary(&x.data, sizeof(x.data))` is equivalent to
`TraceLoggingBinary(&x.data, sizeof(x.data), "&x.data", "", 0)`.

## -see-also

[TraceLoggingWrite](./nf-traceloggingprovider-traceloggingwrite.md)

[TraceLogging wrapper macros](/windows/desktop/tracelogging/tracelogging-wrapper-macros)
