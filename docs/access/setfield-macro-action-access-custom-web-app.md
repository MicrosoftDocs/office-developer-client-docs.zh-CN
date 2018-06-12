---
title: SetField 宏操作 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 9ae292b0-fde0-4c2b-ba23-23e90365597d
description: SetField 操作可用于向字段分配值。
ms.openlocfilehash: 1221ea408540a960b948d2d3ece272fd71cb3daf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773607"
---
# <a name="setfield-macro-action-access-custom-web-app"></a><span data-ttu-id="6c518-103">SetField 宏操作 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="6c518-103">SetField Macro Action (Access custom web app)</span></span>

<span data-ttu-id="6c518-104">**SetField** 操作可用于向字段分配值。</span><span class="sxs-lookup"><span data-stu-id="6c518-104">The **SetField** action can be used to assign a value to a field.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="6c518-p101">[!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="6c518-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="6c518-107">[!注释] **SetField** 操作仅适用于数据宏。</span><span class="sxs-lookup"><span data-stu-id="6c518-107">The **SetField** action is available only in Data Macros.</span></span> 
  
## <a name="setting"></a><span data-ttu-id="6c518-108">设置</span><span class="sxs-lookup"><span data-stu-id="6c518-108">Setting</span></span>

<span data-ttu-id="6c518-109">下表列出了 **SetField** 操作的相关参数。</span><span class="sxs-lookup"><span data-stu-id="6c518-109">The **SetField** action has the arguments listed in the following table.</span></span> 
  
|<span data-ttu-id="6c518-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="6c518-110">**Argument name**</span></span>|<span data-ttu-id="6c518-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c518-111">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c518-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="6c518-112">**Name**</span></span> <br/> |<span data-ttu-id="6c518-113">一个用于标识字段的字符串。</span><span class="sxs-lookup"><span data-stu-id="6c518-113">A string that identifies the field.</span></span>  <br/> |
|<span data-ttu-id="6c518-114">**值**</span><span class="sxs-lookup"><span data-stu-id="6c518-114">**Value**</span></span> <br/> |<span data-ttu-id="6c518-115">一个表达式，指定要分配到的域的值。</span><span class="sxs-lookup"><span data-stu-id="6c518-115">An expression that specifies the value to assign to the field.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6c518-116">备注</span><span class="sxs-lookup"><span data-stu-id="6c518-116">Remarks</span></span>

<span data-ttu-id="6c518-117">不能**[CreateRecord](createrecord-data-block-access-custom-web-app.md)** 或**[EditRecord](editrecord-data-block-access-custom-web-app.md)** 数据块外部使用**SetField**操作。</span><span class="sxs-lookup"><span data-stu-id="6c518-117">The **SetField** action cannot be used outside of a **[CreateRecord](createrecord-data-block-access-custom-web-app.md)** or **[EditRecord](editrecord-data-block-access-custom-web-app.md)** data block.</span></span> 
  

