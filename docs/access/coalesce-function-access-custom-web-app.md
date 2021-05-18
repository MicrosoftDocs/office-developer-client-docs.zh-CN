---
title: '将 Access 自定义 (应用程序功能与) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 92a7cc0a-1f9f-4969-8439-56a8d18e1347
description: 从参数列表中返回非 NULL 的第一个表达式。
ms.openlocfilehash: af309d2330f5c3b3999a4d99d8f2ab2d6d7d61db
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411391"
---
# <a name="coalesce-function-access-custom-web-app"></a><span data-ttu-id="948df-103">将 Access 自定义 (应用程序功能与) </span><span class="sxs-lookup"><span data-stu-id="948df-103">Coalesce function (Access custom web app)</span></span>

<span data-ttu-id="948df-104">从参数列表中返回非 NULL 的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="948df-104">Returns the first expression that is not NULL from a list of arguments.</span></span>
  
> [!NOTE]
> <span data-ttu-id="948df-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="948df-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="948df-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="948df-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="948df-107">语法</span><span class="sxs-lookup"><span data-stu-id="948df-107">Syntax</span></span>

<span data-ttu-id="948df-108">**Coalesce** (*Value*， [*Value*]， ...，[*Value*]) </span><span class="sxs-lookup"><span data-stu-id="948df-108">**Coalesce** (*Value*, [*Value*], …,[*Value*])</span></span> 
  
<span data-ttu-id="948df-109">**Coalesce** 函数包含下列参数</span><span class="sxs-lookup"><span data-stu-id="948df-109">The **Coalesce** function contains the following arguments</span></span> 
  
|<span data-ttu-id="948df-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="948df-110">**Argument name**</span></span>|<span data-ttu-id="948df-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="948df-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="948df-112">*值*</span><span class="sxs-lookup"><span data-stu-id="948df-112">*Value*</span></span>  <br/> |<span data-ttu-id="948df-113">表达式。</span><span class="sxs-lookup"><span data-stu-id="948df-113">An expression.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="948df-114">备注</span><span class="sxs-lookup"><span data-stu-id="948df-114">Remarks</span></span>

<span data-ttu-id="948df-115">如果所有参数都为 NULL， **则 Coalesce** 返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="948df-115">If all arguments are NULL, **Coalesce** returns NULL.</span></span> 
  
## <a name="example"></a><span data-ttu-id="948df-116">示例</span><span class="sxs-lookup"><span data-stu-id="948df-116">Example</span></span>

<span data-ttu-id="948df-117">下面的表达式用作表的验证规则。</span><span class="sxs-lookup"><span data-stu-id="948df-117">The following expression is used as the validation rule for a table.</span></span> <span data-ttu-id="948df-118">该表达式确保在提交记录之前，在"名字、姓氏、电子邮件、移动电话、工作单位电话、住宅电话和公司"字段中输入条目。</span><span class="sxs-lookup"><span data-stu-id="948df-118">The expression ensures that entries are made in the First Name, Last Name, Email, Mobile Phone, Work Phone, Home Phone, and Company fields before a record is committed.</span></span> <span data-ttu-id="948df-119">如果列出的任何字段留空， **则 Coalesce** 函数将返回 Null，这将违反验证规则。</span><span class="sxs-lookup"><span data-stu-id="948df-119">If any of the listed fields are left blank, the **Coalesce** function returns Null, which violates the validation rule.</span></span> 
  
```vb
Coalesce([First Name],[Last Name],[Email],[Mobile Phone],[Work Phone],[Home Phone],[Company]) Is Not Null
```


