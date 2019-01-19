---
title: IS [NOT] NULL（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: b941a0c7-9753-4920-bb6d-cbba94ba9422
description: 确定指定的表达式是否为 NULL。
localization_priority: Priority
ms.openlocfilehash: fe6a0fe4f182a1385304b783e7cfaaf515f732d4
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28699315"
---
# <a name="is-not-null-access-custom-web-app"></a><span data-ttu-id="53ff2-103">IS [NOT] NULL（Access 自定义 Web 应用）</span><span class="sxs-lookup"><span data-stu-id="53ff2-103">IS [NOT] NULL (Access 2013 custom web app)</span></span>

<span data-ttu-id="53ff2-104">确定指定的表达式是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="53ff2-104">Determines whether a specified expression is NULL.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="53ff2-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="53ff2-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="53ff2-107">语法</span><span class="sxs-lookup"><span data-stu-id="53ff2-107">Syntax</span></span>

 <span data-ttu-id="53ff2-108">*expression* **IS** [  *NOT*  ] **NULL**</span><span class="sxs-lookup"><span data-stu-id="53ff2-108">*expression* **IS** [  *NOT*  ] **NULL**</span></span>
  
<span data-ttu-id="53ff2-109">**IS [NOT] NULL** 谓词包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="53ff2-109">The **IS [NOT] NULL** predicate contains the following arguments.</span></span> 
  
|||
|:-----|:-----|
| <span data-ttu-id="53ff2-110">*expression*</span><span class="sxs-lookup"><span data-stu-id="53ff2-110">*expression*</span></span>  <br/> |<span data-ttu-id="53ff2-111">任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="53ff2-111">Any valid expression.</span></span>  <br/> |
| <span data-ttu-id="53ff2-112">*NOT*</span><span class="sxs-lookup"><span data-stu-id="53ff2-112">*NOT*</span></span>  <br/> |<span data-ttu-id="53ff2-113">指定布尔结果取反。</span><span class="sxs-lookup"><span data-stu-id="53ff2-113">Specifies that the Boolean result be negated.</span></span> <span data-ttu-id="53ff2-114">该谓词将对其返回值取反，如果值为非 NULL，则返回 TRUE，如果值为 NULL，则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="53ff2-114">The predicate reverses its return values, returning TRUE if the value is not NULL, and FALSE if the value is NULL.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="53ff2-115">备注</span><span class="sxs-lookup"><span data-stu-id="53ff2-115">Remarks</span></span>

<span data-ttu-id="53ff2-116">如果 *expression* 的值为 NULL，则 IS NULL 返回 TRUE；否则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="53ff2-116">If the value of  *expression*  is NULL, IS NULL returns TRUE; otherwise, it returns FALSE.</span></span> 
  
<span data-ttu-id="53ff2-117">如果 expression 的值为 NULL，则 IS NULL 返回 TRUE；否则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="53ff2-117">If the value of expression is NULL, IS NOT NULL returns FALSE; otherwise, it returns TRUE.</span></span>
  

