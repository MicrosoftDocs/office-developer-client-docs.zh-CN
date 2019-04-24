---
title: 常量 (忙/闲 API)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: 本主题包含常量定义、类标识符和用于闲/忙 API 的接口标识符。
ms.openlocfilehash: 13578617eaab45e7194d7a0d4d6995ef925e7f20
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317715"
---
# <a name="constants-freebusy-api"></a>常量 (忙/闲 API)

本主题包含常量定义、类标识符和用于闲/忙 API 的接口标识符。
  
## <a name="constants"></a>常量

|**常量**|**定义**|
|:-----|:-----|
|E_NOTIMPL  <br/> | *如 Microsoft Windows 软件开发工具包 (SDK) 头文件 winerror.h 中所定义。*  <br/> |
|E_OUTOFMEMORY  <br/> | *如 Windows SDK 头文件 winerror.h 中所定义。*  <br/> |
|S_FALSE  <br/> | *如 Windows SDK 头文件 winerror.h 中所定义。*  <br/> |
|S_OK  <br/> | *如 Windows SDK 头文件 winerror.h 中所定义。*  <br/> |
   
## <a name="interface-identifiers"></a>接口标识符

对于下列接口标识符, 假定在 Windows SDK 头文件 guiddef.h 中定义的 DEFINE_GUID 宏将 GUID 符号名称与它的值关联。
  
{00067064-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IEnumFBBlock、0x00067064、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);
  
{00067066-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusyData、0x00067066、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);
  
{00067067-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusySupport、0x00067067、0x0、0x0、0xc0、0x0、0x0、0x0、0x0、0x0、0x0、0x46);
  

