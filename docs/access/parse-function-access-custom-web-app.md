---
title: 分析函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: 分析的文本值并在给定类型使用的区域性设置的应用程序中返回其值。
ms.openlocfilehash: fa3c453f1faeadca173aaace513ee5ba9115c5fe
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773585"
---
# <a name="parse-function-access-custom-web-app"></a><span data-ttu-id="fc086-103">分析函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="fc086-103">Parse Function (Access custom web app)</span></span>

<span data-ttu-id="fc086-104">分析的文本值并在给定类型使用的区域性设置的应用程序中返回其值。</span><span class="sxs-lookup"><span data-stu-id="fc086-104">Parses a text value and returns its value in a given type using the culture of the application.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fc086-105">本文中所述的云存储功能不再支持在 Office 2013 和 Office 2016 中，可能会导致以下错误： >*对不起，我们在遇到服务器问题，因此我们不能添加\<服务\>立即。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="fc086-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="fc086-106">> 的 Office Online、 iOS，面向 Office 和 Office for Android 云存储，您可以查看到我们[Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="fc086-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fc086-107">语法</span><span class="sxs-lookup"><span data-stu-id="fc086-107">Syntax</span></span>

 <span data-ttu-id="fc086-108">**分析**(*TextExpression*，*数据类型*)</span><span class="sxs-lookup"><span data-stu-id="fc086-108">**Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="fc086-109">**Parse**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="fc086-109">The **Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="fc086-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="fc086-110">**Argument name**</span></span>|<span data-ttu-id="fc086-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="fc086-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="fc086-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="fc086-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="fc086-113">一个文本表达式，表示要分析到指定的数据类型的格式化的值。</span><span class="sxs-lookup"><span data-stu-id="fc086-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="fc086-114">*数据类型*</span><span class="sxs-lookup"><span data-stu-id="fc086-114">*DataType*</span></span>  <br/> |<span data-ttu-id="fc086-115">表示请求结果的数据类型的文本值。</span><span class="sxs-lookup"><span data-stu-id="fc086-115">Literal value representing the data type requested for the result.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fc086-116">备注</span><span class="sxs-lookup"><span data-stu-id="fc086-116">Remarks</span></span>

<span data-ttu-id="fc086-117">**分析**仅用于从字符串转换为日期/时间和号码的类型。</span><span class="sxs-lookup"><span data-stu-id="fc086-117">Use **Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="fc086-118">常规类型转换，使用**转换**函数。</span><span class="sxs-lookup"><span data-stu-id="fc086-118">For general type conversions, use the **Convert** function.</span></span> <span data-ttu-id="fc086-119">请记住，某些性能开销在没有分析的字符串值。</span><span class="sxs-lookup"><span data-stu-id="fc086-119">Keep in mind that there is a certain performance overhead in parsing the string value.</span></span> 
  

