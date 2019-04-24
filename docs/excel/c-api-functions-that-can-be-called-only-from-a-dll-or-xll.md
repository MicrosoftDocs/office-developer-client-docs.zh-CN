---
title: 只能从 DLL 或 XLL 调用的 C API 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 函数 [excel 2007], c api 从 dll 或 xll 调用
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6d2d3c824c482e3726cdaefa869393002a80f44
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32301650"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a>只能从 DLL 或 XLL 调用的 C API 函数

**适用于** Excel 2013 | Office 2013 | Visual Studio 
  
C API 提供了15个 Microsoft Excel 回调函数, 只能通过使用**Excel4**、 **Excel4v**、 **Excel12**或**Excel12v**函数 (或通过使用框架函数 Excel 间接使用这些函数之一) 来调用**** 或**Excel12f**)。 这意味着只能从 DLL 或 XLL 调用它们。
  
## <a name="in-this-section"></a>本节内容

[xlAbort](xlabort.md)
  
[xlAsyncReturn](xlasyncreturn.md)
  
[xlCoerce](xlcoerce.md)
  
[xlDefineBinaryName](xldefinebinaryname.md)
  
[xlDisableXLMsgs](xldisablexlmsgs.md)
  
[xlEnableXLMsgs](xlenablexlmsgs.md)
  
[xlEventRegister](xleventregister.md)
  
[xlFree](xlfree.md)
  
[xlGetBinaryName](xlgetbinaryname.md)
  
[xlGetHwnd](xlgethwnd.md)
  
[xlGetInst](xlgetinst.md)
  
[xlGetInstPtr](xlgetinstptr.md)
  
[xlGetName](xlgetname.md)
  
[xlRunningOnCluster](xlrunningoncluster.md)
  
[xlSet](xlset.md)
  
[xlSheetId](xlsheetid.md)
  
[xlSheetNm](xlsheetnm.md)
  
[xlStack](xlstack.md)
  
[xlUDF](xludf.md)
  
## <a name="see-also"></a>另请参阅



[C API 回调函数 Excel4、Excel12](c-api-callback-functions-excel4-excel12.md)

