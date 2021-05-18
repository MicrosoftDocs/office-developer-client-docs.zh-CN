---
title: 只能从 DLL 或 XLL 调用的 C API 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- functions [excel 2007]， c api called from dll or xll
localization_priority: Normal
ms.assetid: 87c9e75b-c364-4428-a169-010886313b85
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e6d2d3c824c482e3726cdaefa869393002a80f44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423116"
---
# <a name="c-api-functions-that-can-be-called-only-from-a-dll-or-xll"></a>只能从 DLL 或 XLL 调用的 C API 函数

**适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
C API 提供 15 Microsoft Excel 回调函数，这些回调函数只能使用 Excel4、Excel4v、Excel12 或 **Excel12v** 函数 (或这些函数之一间接使用 Framework 函数 Excel 或 **Excel12f**) 调用。   这意味着只能从 DLL 或 XLL 调用它们。
  
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

