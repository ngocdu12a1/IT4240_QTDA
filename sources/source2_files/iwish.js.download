iWish$(document).ready(function () {
	iWishCheck();
	iWishCheckInCollection();
	// if change variant
	iWish$(".iWishAdd").parents('form').find("[name='id']").change(function () {
	    iWishCheck();
	});
	iWish$(".iWishAdd").parents('form').find("[name='variantId']").change(function () {
	    iWishCheck();
	});
	iWish$('.single-option-selector').change(function () {
	    iWishCheck();
	});

	if (iWish$(".iWishView").length > 0) {
		iWish$(".iWishView").click(function () {
			if (iwish_cid == 0) {
				iWishGotoStoreLogin();
			} else {
				iWishSubmit(iWishLink, { cust: iwish_cid });
			}
			return false;
		});
	}

	iWish$(".iWishAdd").click(function () {
		var iWishvId = iWish$(this).parents('form').find("[name='id']").val();
		if (typeof iWishvId === 'undefined') {
			iWishvId = iWish$(this).parents('form').find("[name='variantId']").val();
		};
		var iWishpId = iWish$(this).attr('data-product');
		if (typeof iWishvId === 'undefined') {
		    iWishvId = iWish$(this).attr('data-variant');
		}
		if (typeof iWishvId === 'undefined' || typeof iWishpId === 'undefined') {
			return false;
		}
		if (iwish_cid == 0) {
			iWishGotoStoreLogin();
		} else {
			var postObj = {
				actionx : 'add',
				cust: iwish_cid,
				pid: iWishpId,
				vid: iWishvId
			};
			iWish$.post(iWishLink, postObj, function (data) {
			    if (iWishFindAndGetVal('#iwish_post_result', data) == undefined) return;
				var result = (iWishFindAndGetVal('#iwish_post_result', data).toString().toLowerCase() === 'true');
				var redirect = parseInt(iWishFindAndGetVal('#iwish_post_redirect', data), 10);
				if (result) {
				    iWish$.each(iWish$('.iWishAdd'), function () {
				        var _item = $(this);
				        if (_item.attr('data-variant') == iWishvId) {
				            _item.addClass('iWishHidden'), _item.parent().find('.iWishAdded').removeClass('iWishHidden');
				        }
				    });
				    if (Bizweb.template == "product") {
				        if (redirect == 2) {
				            iWishSubmit(iWishLink, { cust: iwish_cid });
				        }
				    }
				}
			}, 'html');
		}
		return false;
	});
	iWish$(".iWishAdded").click(function () {
	    var iWishvId = iWish$(this).parents('form').find("[name='id']").val();
	    if (typeof iWishvId === 'undefined') {
	        iWishvId = iWish$(this).parents('form').find("[name='variantId']").val();
	    };
	    var iWishpId = iWish$(this).attr('data-product');
	    if (typeof iWishvId === 'undefined') {
	        iWishvId = iWish$(this).attr('data-variant');
	    }
	    if (typeof iWishvId === 'undefined' || typeof iWishpId === 'undefined') {
	        return false;
	    }
	    if (iwish_cid == 0) {
	        iWishGotoStoreLogin();
	    } else {
	        var postObj = {
	            actionx: 'remove',
	            cust: iwish_cid,
	            pid: iWishpId,
	            vid: iWishvId
	        };
	        iWish$.post(iWishLink, postObj, function (data) {
	            if (iWishFindAndGetVal('#iwish_post_result', data) == undefined) return;
	            var result = (iWishFindAndGetVal('#iwish_post_result', data).toString().toLowerCase() === 'true');
	            var redirect = parseInt(iWishFindAndGetVal('#iwish_post_redirect', data), 10);
	            if (result) {
	                iWish$.each(iWish$('.iWishAdd'), function () {
	                    var _item = $(this);
	                    if (_item.attr('data-variant') == iWishvId) {
	                        _item.removeClass('iWishHidden'), _item.parent().find('.iWishAdded').addClass('iWishHidden');
	                    }
	                });
	            }
	        }, 'html');
	    }
	    return false;
	});
});
$(document).ready(function () {
	$('.single-option-selector').change(function () {
		iWishCheck();
	});
});
