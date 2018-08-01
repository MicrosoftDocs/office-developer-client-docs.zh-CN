---
title: 合并函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 92a7cc0a-1f9f-4969-8439-56a8d18e1347
description: 返回不为 NULL 从参数列表的第一个表达式。
ms.openlocfilehash: cfe6f59c22a89b2a6d211e5f05c2dbf275d8da11
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773447"
---
# <a name="coalesce-function-access-custom-web-app"></a><span data-ttu-id="959f9-103">合并函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="959f9-103">Coalesce function (Access custom web app)</span></span>

<span data-ttu-id="959f9-104">返回不为 NULL 从参数列表的第一个表达式。</span><span class="sxs-lookup"><span data-stu-id="959f9-104">Returns the first expression that is not NULL from a list of arguments.</span></span>
  
> [!NOTE]
> <span data-ttu-id="959f9-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="959f9-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="959f9-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="959f9-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="959f9-107">语法</span><span class="sxs-lookup"><span data-stu-id="959f9-107">Syntax</span></span>

<span data-ttu-id="959f9-108">**合并**（*值*，[*值*]，...，[*值*]）</span><span class="sxs-lookup"><span data-stu-id="959f9-108">**Coalesce** (*Value*, [*Value*], …,[*Value*])</span></span> 
  
<span data-ttu-id="959f9-109">**联合**函数包含以下参数</span><span class="sxs-lookup"><span data-stu-id="959f9-109">The **Coalesce** function contains the following arguments</span></span> 
  
|<span data-ttu-id="959f9-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="959f9-110">**Argument name**</span></span>|<span data-ttu-id="959f9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="959f9-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="959f9-112">*Value*</span><span class="sxs-lookup"><span data-stu-id="959f9-112">*Value*</span></span>  <br/> |<span data-ttu-id="959f9-113">一个表达式。</span><span class="sxs-lookup"><span data-stu-id="959f9-113">An expression.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="959f9-114">说明</span><span class="sxs-lookup"><span data-stu-id="959f9-114">Remarks</span></span>

<span data-ttu-id="959f9-115">如果所有参数都均为空，**联合**将返回 NULL。</span><span class="sxs-lookup"><span data-stu-id="959f9-115">If all arguments are NULL, **Coalesce** returns NULL.</span></span> 
  
## <a name="example"></a><span data-ttu-id="959f9-116">示例</span><span class="sxs-lookup"><span data-stu-id="959f9-116">Example</span></span>

<span data-ttu-id="959f9-117">以下表达式用作表格的有效性规则。</span><span class="sxs-lookup"><span data-stu-id="959f9-117">The following expression is used as the validation rule for a table.</span></span> <span data-ttu-id="959f9-118">表达式可确保提交记录之前的项所做的名字，最后一个名称，电子邮件，移动电话，工作电话，家庭电话、 和公司字段中。</span><span class="sxs-lookup"><span data-stu-id="959f9-118">The expression ensures that entries are made in the First Name, Last Name, Email, Mobile Phone, Work Phone, Home Phone, and Company fields before a record is committed.</span></span> <span data-ttu-id="959f9-119">如果任一列出的字段为空，则**联合**函数将返回 Null，违反有效性规则。</span><span class="sxs-lookup"><span data-stu-id="959f9-119">If any of the listed fields are left blank, the **Coalesce** function returns Null, which violates the validation rule.</span></span> 
  
```vb
Coalesce([First Name],[Last Name],[Email],[Mobile Phone],[Work Phone],[Home Phone],[Company]) Is Not Null
```


