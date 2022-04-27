# Evmos Mainnet snapshot install guide

## Step 1 - Stop Evmos service

```
systemctl stop evmosd.service

```

## Step 2 - Delete old data

```
rm -rf ~/.evmosd/data; \
mkdir -p ~/.evmosd/data; \
cd ~/.evmosd/data

```

## Step 3 - Download snapshot

```
LATEST_SNAPSHOT=$(curl -s https://snapshots.stakingcare.com/evmos/mainnet/ | egrep -o ">evmos.*tar" | tr -d ">" | tail -n1)
wget -O - https://snapshots.stakingcare.com/evmos/mainnet/${LATEST_SNAPSHOT} | tar xf -

```

## Step 4 -  Start Evmos service

```
systemctl start evmosd.service

```
