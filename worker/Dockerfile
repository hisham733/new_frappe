ARG FRAPPE_BRANCH=version-12
FROM frappe/erpnext-worker:${FRAPPE_BRANCH}

ARG GITHUB_OWNER=msf4-0
ENV GITHUB_OWNER=$GITHUB_OWNER

# Copy custom ERPNext changes
COPY ./custom_erpnext /home/frappe/frappe-bench/apps/erpnext

# Install additional apps
RUN install_app metabase_integration https://github.com/${GITHUB_OWNER}/ERPNext-Metabase-Integration master && \
    install_app erpnext_telegram_integration https://github.com/${GITHUB_OWNER}/ERPNext-Telegram-Integration master && \
    install_app frepple https://github.com/${GITHUB_OWNER}/ERPNext-Frepple-Enhanced-Integration main && \
    install_app sql_accounting_software https://github.com/${GITHUB_OWNER}/ERPNext-SQL-Accounting-Integration main && \
    install_app barcode_shrdc https://github.com/${GITHUB_OWNER}/ERPNext-Barcode-Integration master && \
    install_app autocount https://github.com/${GITHUB_OWNER}/ERPNext-Autocount-Integration master && \
    install_app short_courses https://github.com/Shakila-Sahira/ERPNext-Short-Courses && \
    install_app e_invoice_erp https://github.com/hisham733/E-Invoice-ERP

