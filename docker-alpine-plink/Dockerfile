FROM alpine:3.10.3

# Install Dependencies
RUN apk update && apk upgrade && \
    apk add --no-cache bash curl coreutils

# Install Plink and add in PATH
Run curl -sO http://zzz.bwh.harvard.edu/plink/dist/plink-1.07-x86_64.zip && \
    unzip -qq plink-1.07-x86_64.zip && \
    rm -rf plink-1.07-*.zip && \
    cp plink-1.07-*/plink /bin/ && \
    rm -rf plink-1.07-*

