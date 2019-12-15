// Có thể sửa function abAvailableNoticeVariantChange() để thay đổi thông báo khi chọn variant
function abAvailableNoticeVariantChange() {
    $('.single-option-selector').change(function () {
        if (typeof ABAvailableNotice !== 'undefined' && typeof ABAvailableNotice.getAndCheckProduct !== 'undefined') {
            ABAvailableNotice.getAndCheckProduct();
        }
    });
}
//

$(document).ready(function () {
    abAvailableNoticeVariantChange();
});
