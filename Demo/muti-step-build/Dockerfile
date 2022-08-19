FROM busybox AS buildFile
RUN touch dummy.txt
RUN echo "dummy">/dummy.txt

FROM busybox
COPY --from=buildFile /dummy.txt ./
CMD ["cat", "./dummy.txt"]