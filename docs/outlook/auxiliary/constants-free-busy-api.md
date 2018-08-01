---
title: 常量 (忙/闲 API)
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: ff756bf1-9395-5e50-4f55-1eb0365a84ed
description: 本主题包含忙/闲 api 常量定义、 类标识符和界面标识符。
ms.openlocfilehash: ec909d449dc9075959fc9c047457577efd52ec3a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774178"
---
# <a name="constants-freebusy-api"></a>常量 (忙/闲 API)

本主题包含忙/闲 api 常量定义、 类标识符和界面标识符。
  
## <a name="constants"></a>常量

|**常量**|**定义**|
|:-----|:-----|
|E_NOTIMPL  <br/> | *Microsoft Windows 软件开发工具包 (SDK) 标头文件 winerror.h 中定义。*  <br/> |
|E_OUTOFMEMORY  <br/> | *Windows SDK 标头文件 winerror.h 中定义。*  <br/> |
|S_FALSE  <br/> | *Windows SDK 标头文件 winerror.h 中定义。*  <br/> |
|S_OK  <br/> | *Windows SDK 标头文件 winerror.h 中定义。*  <br/> |
   
## <a name="interface-identifiers"></a>界面标识符

以下接口标识符，假定其值与相关联的 GUID 的符号名称 Windows SDK 标头文件 guiddef.h 中定义的 DEFINE_GUID 宏。
  
{00067064-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IEnumFBBlock，0x00067064 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);
  
{00067066-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusyData，0x00067066 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);
  
{00067067-0000-0000-C000-000000000046}
  
DEFINE_GUID (IID_IFreeBusySupport，0x00067067 0x0、 0x0、 0xc0，0x0、 0x0、 0x0、 0x0、 0x0、 0x0、 0x46);
  

